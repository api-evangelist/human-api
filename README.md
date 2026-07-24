# Human API (human-api)

Human API is a United States health data platform, founded in 2013 and now part of LexisNexis Risk Solutions, that aggregates, normalizes, and delivers digital and clinical health data from providers, hospitals, labs, pharmacies, wearables, and apps through a single API. Its consumer-mediated Data API returns normalized wellness and medical records via user access tokens (Human Connect single sign-on), while its Health Intelligence Platform (HIP) Admin API lets enterprises order electronic health record (EHR) retrievals, manage users and subscriptions, and receive condensed clinical summary reports — primarily to accelerate life insurance underwriting across 30,000+ data sources. The surface is a proprietary REST/JSON API secured with OAuth2-style client credentials and Bearer JWT tokens; it is not a HL7 FHIR or SMART-on-FHIR API, and access is gated behind a developer portal and partner agreement.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/human-api/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/human-api/refs/heads/main/apis.yml)

## Tags

- Healthcare
- United States
- Health Data
- EHR
- Interoperability
- Remote Monitoring
- Wearables
- Life Insurance
- Clinical Data
- Health API

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Human API Admin API

The Health Intelligence Platform (HIP) Admin API for creating and managing Human API users, submitting and managing EHR order types, managing subscriptions, and fetching delivered clinical summary reports and order resources. Secured with a Bearer JWT.

- **Human URL:** [https://reference.humanapi.co/docs/overview](https://reference.humanapi.co/docs/overview)
- **Base URL:** `https://admin.humanapi.co`

#### Properties

- [Documentation](https://reference.humanapi.co/docs/overview)
- [API Reference](https://reference.humanapi.co/reference/getordertypes)
- [OpenAPI](openapi/human-api-admin-order-types-openapi.json)
- [OpenAPI](openapi/human-api-admin-users-list-openapi.json)
- [OpenAPI](openapi/human-api-admin-user-reports-openapi.json)

### Human API Authentication API

The HAPI Auth Public API for facilitating token exchange with external authentication systems — `POST /v1/admin/token` (Admin API client-type token) and `POST /v1/connect/token` (public Connect token with optional extra scopes).

- **Human URL:** [https://reference.humanapi.co/docs/overview](https://reference.humanapi.co/docs/overview)
- **Base URL:** `https://auth.humanapi.co`

#### Properties

- [Documentation](https://reference.humanapi.co/docs/overview)
- [OpenAPI](openapi/human-api-auth-admin-token-openapi.json)
- [OpenAPI](openapi/human-api-auth-connect-token-openapi.json)

### Human API Data API

The consumer-mediated Data API (legacy v2.1) for querying a user's normalized health data — wellness data from wearable devices and apps, and medical data (records, labs, medications, encounters) from health providers, using the user's accessToken as a Bearer credential.

- **Human URL:** [https://reference.humanapi.co/v2.1/docs/data-overview](https://reference.humanapi.co/v2.1/docs/data-overview)
- **Base URL:** `https://api.humanapi.co/v1/human`

#### Properties

- [Documentation](https://reference.humanapi.co/v2.1/docs/data-overview)
- [API Reference](https://reference.humanapi.co/v2.1/docs/overview)

## Common Properties

- [Website](https://humanapi.co/)
- [Developer Portal](https://developer.humanapi.co/)
- [Documentation](https://reference.humanapi.co/)
- [API Reference](https://reference.humanapi.co/docs/overview)
- [Getting Started](https://reference.humanapi.co/docs/integration-best-practices)
- [GitHub Organization](https://github.com/humanapi)
- [Status Page](https://status.humanapi.co/)
- [Login](https://developer.humanapi.co/)
- [Terms of Service](https://www.humanapi.co/developer-terms)
- [Privacy Policy](https://humanapi.co/privacy-policy)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
