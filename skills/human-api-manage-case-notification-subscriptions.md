---
name: Subscribe case managers to Human API case notifications
description: Create, look up and remove Human API subscriptions so field agents and case managers are notified about an applicant's progress through the EHR retrieval process.
api: openapi/human-api-admin-subscription-create-openapi.json
operations: [createSubscription, getUsersSubscriptions, getSubscriptionDetails, deleteSubscription]
---

# Subscribe case managers to Human API case notifications

Operating instructions for the subscriptions surface of the Human API HIP Admin API. All
paths are on `https://admin.humanapi.co`; auth is minted on `https://auth.humanapi.co`.

**What a subscription is.** A Human API subscription binds a **named human** — an agent,
producer or case manager, identified by email and role — to a case identified by
`clientUserId`, so they are kept informed about the applicant's progress. It is **not** a
webhook endpoint registration. Machine notification delivery (Order Summary, APS Status
Notes) is configured out-of-band with an Account Manager; see
`asyncapi/human-api-notifications-asyncapi.yml`.

## 1. Authenticate
`POST https://auth.humanapi.co/v1/admin/token` → Bearer JWT (`bearerAuth`) on every call.

## 2. Create the subscription
`createSubscription` — `POST /api/v1/subscriptions` with
`{ "clientUserId", "subscriberEmail", "subscriberFirstName", "subscriberLastName",
"subscriberOffice", "role" }`. Returns `201` with an array of subscription objects.
A `409 Conflict` means the subscription already exists — treat it as success, not as an error
to retry, because there is no idempotency key on this API.

## 3. Find existing subscriptions
`getUsersSubscriptions` — `GET /api/v1/subscriptions` finds subscriptions. Always look before
creating: repeated creates are the main way duplicate notification recipients appear.

## 4. Read one subscription
`getSubscriptionDetails` — `GET /api/v1/subscriptions/{subscriptionId}`.

## 5. Remove it
`deleteSubscription` — `DELETE /api/v1/subscriptions/{subscriptionId}`. **Destructive and not
reversible through the API** — the recipient silently stops receiving case updates. Confirm
the subscriptionId with step 4 first.

## Runtime notes
- Errors: `400` (bad request / `errorInvalidInput` with `validation.keys[]`), `401` (expired
  or revoked token), `404` (unknown id), `409` (conflict). See
  `errors/human-api-problem-types.yml`.
- Subscriber email addresses are personal data attached to a health-records case; handle them
  under the same controls as the report content itself.
