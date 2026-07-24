---
name: Connect a user and read their normalized health data
description: Mint a Human Connect token for an end user, let them link their health data sources, then query their normalized wellness and medical data from the consumer Data API.
api: openapi/human-api-auth-connect-token-openapi.json
operations: [getUsersList]
---

# Connect a user and read their normalized health data

Operating instructions for the consumer-mediated flow: Human Connect (data-source linking)
plus the legacy v2.1 Data API (`https://api.humanapi.co/v1/human`).

## 1. Mint a Connect token
`POST https://auth.humanapi.co/v1/connect/token` with
`{ "client_id", "client_user_id", "type", optional: "client_secret", "client_user_email", "extra_scopes" }`.
This returns a token used to spawn Human Connect for that specific end user.

## 2. Launch Human Connect
Embed the Human Connect widget (`humanapi-connect-client`, see
`components/human-api-components.yml`) using the token. The user authenticates their
providers, labs, pharmacies, wearables, and apps. On success you receive the user's
`accessToken`.

## 3. Query normalized health data
Call the Data API with the user's `accessToken` as `Authorization: Bearer <accessToken>`
against `https://api.humanapi.co/v1/human` — wellness data (devices/apps) and medical data
(records, labs, medications, encounters), normalized across sources.

## 4. (Admin) reconcile users
On the Admin side, `getUsersList` (`GET /api/v1/users`, filter by `clientUserId`) reconciles
the connected user back to your records.

## Conventions & errors
- Unauthenticated Data API requests return 401; the root redirects (302) to `/v1/human`.
- This is a proprietary normalized model, NOT FHIR/SMART-on-FHIR.
- Error envelope and tracing: see `conventions/human-api-conventions.yml`.
