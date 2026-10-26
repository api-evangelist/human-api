# Human API (human-api)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
