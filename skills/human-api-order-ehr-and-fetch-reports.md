---
name: Order an EHR retrieval and fetch the clinical report
description: Authenticate to the Human API HIP Admin API, discover order types, resolve the user, and retrieve the delivered clinical summary report once the order completes.
api: openapi/human-api-admin-order-types-openapi.json
operations: [getOrderTypes, getUsersList, getUserReports]
---

# Order an EHR retrieval and fetch the clinical report

Operating instructions for the Human API Health Intelligence Platform (HIP) Admin API. All
paths are on `https://admin.humanapi.co`; auth is minted on `https://auth.humanapi.co`.

## 1. Authenticate
Mint an Admin API access token: `POST https://auth.humanapi.co/v1/admin/token` with a JSON
body `{ "client_id", "client_secret", "type" }`. Use the returned JWT as
`Authorization: Bearer <token>` on every Admin API call (`bearerAuth`).

## 2. Discover order types
`getOrderTypes` — `GET /api/v1/order-types` returns the EHR order types enabled for your
client app. Pick the order type you intend to submit.

## 3. Resolve the user
`getUsersList` — `GET /api/v1/users` lists active users. Filter by `humanId` or
`clientUserId`, and page with the `offset` parameter. Capture the `humanId`.

## 4. Wait for the order to complete
Orders transition Created -> In Progress -> (Pended) -> Completed/Cancelled. Do not poll
tightly — subscribe to the **Order Summary** webhook (`orders.OrderSummaryUpdated`, see
`asyncapi/human-api-notifications-asyncapi.yml`), which fires when the order reaches a
terminal state and reports `reportsAvailable`.

## 5. Fetch the report
`getUserReports` — `GET /api/v1/user/reports` returns the user's available reports; pass
`createdByOrderId` to scope to the order you submitted. Download each report via its `uri`.

## Conventions & errors
- Errors return `{ code, error, message, x-humanapi-request-id }`; log `x-humanapi-request-id`
  for support (see `errors/human-api-problem-types.yml`).
- 401 = expired/invalid Bearer token — re-mint. 404 = unknown user/report.
- No idempotency-key contract is documented; treat report fetches as safe reads.
