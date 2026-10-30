# Human API

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

Human API is a United States health data platform, founded in 2013 and now part of LexisNexis Risk Solutions, that aggregates, normalizes, and delivers digital and clinical health data from providers, hospitals, labs, pharmacies, wearables, and apps through a single API. Its consumer-mediated Data API returns normalized wellness and medical records via user access tokens (Human Connect single sign-on), while its Health Intelligence Platform (HIP) Admin API lets enterprises order electronic health record (EHR) retrievals, manage users and subscriptions, and receive condensed clinical summary reports - primarily to accelerate life insurance underwriting by reaching 30,000+ data sources across roughly 270 million lives. The surface is a proprietary REST/JSON API secured with OAuth2-style client credentials and Bearer JWT tokens; it is not a HL7 FHIR or SMART-on-FHIR API. Access is gated behind a developer portal and partner agreement.

**Areas:** Healthcare · United States · Health Data · Electronic Health Records · Interoperability · Remote Monitoring · Wearables · Life Insurance · Clinical Data · Health API

## Human API on APIs.io

Everything profiled for Human API is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/human-api/](https://apis.io/providers/human-api/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [Human API Data API](https://apis.io/apis/human-api/human-api-data-api/) — The consumer-mediated Data API (legacy v2.1) for querying a user's normalized health data - wellness data from wearable devices and apps, and medical data…
- [Human API Admin API](https://apis.io/apis/human-api/human-api-admin-api/) — API endpoints to authorize a client app for the Admin API
- [Human API Connect API](https://apis.io/apis/human-api/human-api-connect-api/) — API endpoints to generate tokens for Connect App
- [Human API Orders API](https://apis.io/apis/human-api/human-api-orders-api/) — API endpoints to get orders
- [Human API Reports API](https://apis.io/apis/human-api/human-api-reports-api/) — API endpoints to manage user resports
- [Human API Resources API](https://apis.io/apis/human-api/human-api-resources-api/) — API endpoints to request different resources
- [Human API Subscriptions API](https://apis.io/apis/human-api/human-api-subscriptions-api/) — API endpoints to manage subscriptions
- [Human API Users API](https://apis.io/apis/human-api/human-api-users-api/) — API endpoints to manage users

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Human API HIP Notifications](https://apis.io/asyncapis/human-api/human-api-notifications-asyncapi/)

#### Event channels (2)

Individual events and webhooks the provider emits.

- [aps/status-notes](https://apis.io/channels/human-api/aps-status-notes/)
- [order/summary](https://apis.io/channels/human-api/order-summary/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [human-api](https://apis.io/servers/human-api/human-api/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Human Api Agentic Access](https://apis.io/agentic-access/human-api/human-api-agentic-access/)

#### Collections (5)

Postman and Open Collection request collections.

- [Admin API](https://apis.io/collections/human-api/open-human-api-admin-order-types/)
- [Admin API](https://apis.io/collections/human-api/open-human-api-admin-user-reports/)
- [Admin API](https://apis.io/collections/human-api/open-human-api-admin-users-list/)
- [HAPI Auth Public](https://apis.io/collections/human-api/open-human-api-auth-admin-token/)
- [HAPI Auth Public](https://apis.io/collections/human-api/open-human-api-auth-connect-token/)

#### Overlays (15)

OpenAPI overlays, including conversational phrasing for each operation.

- [Human Api Admin Consumer Link Overlay](https://apis.io/overlays/human-api/human-api-admin-consumer-link-overlay/)
- [Human Api Admin Order Types Overlay](https://apis.io/overlays/human-api/human-api-admin-order-types-overlay/)
- [Human Api Admin Report By Id Overlay](https://apis.io/overlays/human-api/human-api-admin-report-by-id-overlay/)
- [Human Api Admin Subscription Create Overlay](https://apis.io/overlays/human-api/human-api-admin-subscription-create-overlay/)
- [Human Api Admin Subscription Delete Overlay](https://apis.io/overlays/human-api/human-api-admin-subscription-delete-overlay/)
- [Human Api Admin Subscription Details Overlay](https://apis.io/overlays/human-api/human-api-admin-subscription-details-overlay/)
- [Human Api Admin Subscriptions List Overlay](https://apis.io/overlays/human-api/human-api-admin-subscriptions-list-overlay/)
- [Human Api Admin User Actions Overlay](https://apis.io/overlays/human-api/human-api-admin-user-actions-overlay/)
- [Human Api Admin User Create Overlay](https://apis.io/overlays/human-api/human-api-admin-user-create-overlay/)
- [Human Api Admin User Details Overlay](https://apis.io/overlays/human-api/human-api-admin-user-details-overlay/)
- [Human Api Admin User Providers Overlay](https://apis.io/overlays/human-api/human-api-admin-user-providers-overlay/)
- [Human Api Admin User Reports Overlay](https://apis.io/overlays/human-api/human-api-admin-user-reports-overlay/)
- [Human Api Admin Users List Overlay](https://apis.io/overlays/human-api/human-api-admin-users-list-overlay/)
- [Human Api Auth Admin Token Overlay](https://apis.io/overlays/human-api/human-api-auth-admin-token-overlay/)
- [Human Api Auth Connect Token Overlay](https://apis.io/overlays/human-api/human-api-auth-connect-token-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Human Api Authentication](https://apis.io/security/human-api/human-api-authentication/)
- [Human Api Domain Security](https://apis.io/security/human-api/human-api-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Human Api Plans Pricing](https://apis.io/plans/human-api/human-api-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Human Api Rate Limits](https://apis.io/rate-limits/human-api/human-api-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://humanapi.co/)
- [Documentation](https://reference.humanapi.co/)
- [Getting started](https://reference.humanapi.co/docs/integration-best-practices)
- [API reference](https://reference.humanapi.co/docs/overview)
- [Support](https://support.humanapi.co/hc/en-us)
- [Compliance](https://reference.humanapi.co/page/epic-documentation)
- [Terms of service](https://www.humanapi.co/developer-terms)
- [Privacy policy](https://humanapi.co/privacy-policy)
- [GitHub](https://github.com/humanapi)
- [Status](https://status.humanapi.co/)

## API Evangelist rating

**Kin Score 51.7** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 57.0 |
| Contract governance | 18.2 |
| Operational transparency | 26.3 |
| Developer ergonomics | 67.3 |
| Access clarity | 38.2 |

**Agent readiness 28.7** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 36.3** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/human-api/](https://apis.io/providers/human-api/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Human API: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/human-api/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
