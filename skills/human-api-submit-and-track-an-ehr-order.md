---
name: Submit an EHR order and track it to a terminal state
description: Create a Human API user with an EHR order (optionally attaching a HIPAA authorization), monitor the fulfillment lifecycle, surface outstanding applicant tasks, and cancel the order if underwriting no longer needs it.
api: openapi/human-api-admin-user-create-openapi.json
operations: [createUser, getUserDetails, performActionForUser, getTasksLiistLink, getOrderTypes]
---

# Submit an EHR order and track it to a terminal state

Operating instructions for the Human API Health Intelligence Platform (HIP) Admin API. All
paths are on `https://admin.humanapi.co`; auth is minted on `https://auth.humanapi.co`.

## 1. Authenticate
`POST https://auth.humanapi.co/v1/admin/token` with `{ "client_id", "client_secret", "type" }`.
Send the returned JWT as `Authorization: Bearer <token>` on every Admin API call (`bearerAuth`).
Note: this operation declares only a `200` response in the provider's spec — its failure
contract is undocumented, so treat any non-200 as opaque and do not retry blindly.

## 2. Choose the order type
`getOrderTypes` — `GET /api/v1/order-types` returns the order types enabled for your client
app. Human API's own guidance recommends configuring at least four: **Complete Medical
Record**, **No Contact**, **APS Only**, **EHR Only**
(see https://reference.humanapi.co/docs/integration-best-practices).

## 3. Create the user and submit the order
`createUser` — `POST /api/v1/users`. The request body carries the applicant identity plus the
order, and may include `attachments[]` with `{ "type": "hipaaAuthorization", "contentType":
"application/pdf", "encoding": "base64", "content": "…" }`. Set `clientUserId` to your own
case/policy identifier and use `clientData` for any correlation metadata you want echoed back
on notifications.

**There is no idempotency key on this API.** A retried create after a timeout is not safe —
it may submit a second billable order. On collision the API returns `409 Conflict`
("Unable to match the login of the new user to an existing user found for that user"); treat
that as "already created", not as a failure to retry. Validation errors return the
**alternate** envelope `{ statusCode, error, message, validation: { source, keys[] } }`, not
the usual `{ code, error, message }` — parse both shapes.

## 4. Track the order
Orders transition **Created → In Progress → (Pended) → Completed / Cancelled**
(https://reference.humanapi.co/docs/order-fulfillment-lifecycle). Do not poll tightly:
subscribe to the **Order Summary** notification (`orders.OrderSummaryUpdated`, see
`asyncapi/human-api-notifications-asyncapi.yml`), which fires on the terminal transition and
reports `orderStatus`, `timedOut`, `reportsAvailable`, `dataAvailable` and `fcraSuppressed`.
Notification payloads arrive as a **JSON array**, not a single object.

`getUserDetails` — `GET /api/v1/users/{humanId}` reads current state when you need a pull.

## 5. Surface outstanding applicant tasks
`getTasksLiistLink` — `POST /api/v1/resources/consumer-link` returns a link the applicant (or
a case manager) can open to see the order's outstanding tasks. The operationId is misspelled
in the provider's own spec; use it verbatim.

## 6. Cancel when underwriting no longer needs it
`performActionForUser` — `POST /api/v1/users/actions`. This is **consequential**: it can abort
an in-flight order. A `409 Conflict` means the order already reached a terminal state
(Cancelled or Completed) and cannot be aborted — check the last Order Summary event before
attempting a cancel.

## Runtime notes
- No published rate limits, no `RateLimit-*`/`Retry-After` headers, no declared `429`.
  Back off conservatively on your own schedule (`rate-limits/human-api-rate-limits.yml`).
- Every error body carries `x-humanapi-request-id`; log it — it is the only support handle.
- Reports contain protected health information. See `conformance/human-api-conformance.yml`
  for the published HIPAA and ONC 45 CFR 170.315 posture.
