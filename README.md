# Eliq

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

Eliq is a Swedish energy-data company (Eliq AB, Gothenburg) that gives utilities and energy-app developers an API layer over household energy data. Its Data Management API ingests users, locations, meters, consumption readings and tariff price formulas — synchronously or as asynchronous NDJSON bulk jobs — and its Insights API returns presentation-ready analytics on top of that data: consumption and cost by day, week, month and year, CO2 footprint, appliance-level disaggregation (NILM), day-ahead market prices, peak power and dynamic capacity, tariff comparison, PV production, forecasting, anomaly detection, similar-homes benchmarking, budgets and personalised advice. An Intelligence API adds portfolio segmentation for utility service and growth teams, and an OAuth 2.0 Auth API issues app and delegated tokens for all of it. Eliq also ships 20 embeddable web components and pushes notification webhooks signed with HMAC-SHA256. Access is commercial — credentials are issued by an account manager — but all four OpenAPI contracts are published publicly.

**Areas:** Energy · Utilities · Analytics · Sustainability · Energy Data · Smart Meter · Disaggregation · Forecasting · Segmentation · Consumption · Tariffs · Insights

## Eliq on APIs.io

Everything profiled for Eliq is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/eliq/](https://apis.io/providers/eliq/)** — or go straight to one of the APIs or properties below.

### APIs (39)

- [Eliq Advice API](https://apis.io/apis/eliq/eliq-advice-api/) — The Advice API from Eliq — 3 operation(s) for advice.
- [Eliq Anomalies API](https://apis.io/apis/eliq/eliq-anomalies-api/) — The Anomalies API from Eliq — 1 operation(s) for anomalies.
- [Eliq Authentication API](https://apis.io/apis/eliq/eliq-authentication-api/) — The Authentication API from Eliq — 2 operation(s) for authentication.
- [Eliq Breakdown API](https://apis.io/apis/eliq/eliq-breakdown-api/) — The Breakdown API from Eliq — 1 operation(s) for breakdown.
- [Eliq Budgets API](https://apis.io/apis/eliq/eliq-budgets-api/) — The Budgets API from Eliq — 2 operation(s) for budgets.
- [Eliq Client details API](https://apis.io/apis/eliq/eliq-client-details-api/) — The Client details API from Eliq — 1 operation(s) for client details.
- [Eliq Dashboards API](https://apis.io/apis/eliq/eliq-dashboards-api/) — The Dashboards API from Eliq — 1 operation(s) for dashboards.
- [Eliq Eliq Connect API](https://apis.io/apis/eliq/eliq-eliq-connect-api/) — The Eliq Connect API from Eliq — 4 operation(s) for eliq connect.
- [Eliq Energy Data API](https://apis.io/apis/eliq/eliq-energy-data-api/) — The Energy Data API from Eliq — 8 operation(s) for energy data.
- [Eliq Energy Performance Certificate API](https://apis.io/apis/eliq/eliq-energy-performance-certificate-api/) — The Energy Performance Certificate API from Eliq — 1 operation(s) for energy performance certificate.
- [Eliq Energy Usage Categories API](https://apis.io/apis/eliq/eliq-energy-usage-categories-api/) — The Energy Usage Categories API from Eliq — 1 operation(s) for energy usage categories.
- [Eliq Health API](https://apis.io/apis/eliq/eliq-health-api/) — The Health API from Eliq — 1 operation(s) for health.
- [Eliq Home Profile API](https://apis.io/apis/eliq/eliq-home-profile-api/) — The Home Profile API from Eliq — 2 operation(s) for home profile.
- [Eliq Info API](https://apis.io/apis/eliq/eliq-info-api/) — The Info API from Eliq — 3 operation(s) for info.
- [Eliq Jobs API](https://apis.io/apis/eliq/eliq-jobs-api/) — The Jobs API from Eliq — 8 operation(s) for jobs.
- [Eliq Location API](https://apis.io/apis/eliq/eliq-location-api/) — The Location API from Eliq — 3 operation(s) for location.
- [Eliq Location home profile API](https://apis.io/apis/eliq/eliq-location-home-profile-api/) — The Location home profile API from Eliq — 1 operation(s) for location home profile.
- [Eliq Location price formulas API](https://apis.io/apis/eliq/eliq-location-price-formulas-api/) — The Location price formulas API from Eliq — 2 operation(s) for location price formulas.
- [Eliq Location profile API](https://apis.io/apis/eliq/eliq-location-profile-api/) — The Location profile API from Eliq — 7 operation(s) for location profile.
- [Eliq Locations API](https://apis.io/apis/eliq/eliq-locations-api/) — The Locations API from Eliq — 8 operation(s) for locations.
- [Eliq Location Segmentation API](https://apis.io/apis/eliq/eliq-locationsegmentation-api/) — The LocationSegmentation API from Eliq — 6 operation(s) for locationsegmentation.
- [Eliq Market Price API](https://apis.io/apis/eliq/eliq-market-price-api/) — The Market Price API from Eliq — 2 operation(s) for market price.
- [Eliq Meter API](https://apis.io/apis/eliq/eliq-meter-api/) — The Meter API from Eliq — 2 operation(s) for meter.
- [Eliq Meter Energy Day API](https://apis.io/apis/eliq/eliq-meter-energy-day-api/) — The Meter Energy Day API from Eliq — 1 operation(s) for meter energy day.
- [Eliq Meter Energy High Resolution API](https://apis.io/apis/eliq/eliq-meter-energy-high-resolution-api/) — The Meter Energy High Resolution API from Eliq — 2 operation(s) for meter energy high resolution.
- [Eliq Meter Energy Period API](https://apis.io/apis/eliq/eliq-meter-energy-period-api/) — The Meter Energy Period API from Eliq — 1 operation(s) for meter energy period.
- [Eliq Meter Energy Reads API](https://apis.io/apis/eliq/eliq-meter-energy-reads-api/) — The Meter Energy Reads API from Eliq — 1 operation(s) for meter energy reads.
- [Eliq Meter Max Demand API](https://apis.io/apis/eliq/eliq-meter-max-demand-api/) — The Meter Max Demand API from Eliq — 2 operation(s) for meter max demand.
- [Eliq Meter Price Formulas API](https://apis.io/apis/eliq/eliq-meter-price-formulas-api/) — The Meter Price Formulas API from Eliq — 3 operation(s) for meter price formulas.
- [Eliq Portfolio Accounts API](https://apis.io/apis/eliq/eliq-portfolio-accounts-api/) — The Portfolio Accounts API from Eliq — 3 operation(s) for portfolio accounts.
- [Eliq Portfolio Groups API](https://apis.io/apis/eliq/eliq-portfolio-groups-api/) — The Portfolio Groups API from Eliq — 2 operation(s) for portfolio groups.
- [Eliq Portfolio Locations API](https://apis.io/apis/eliq/eliq-portfolio-locations-api/) — The Portfolio Locations API from Eliq — 2 operation(s) for portfolio locations.
- [Eliq Portfolio Users API](https://apis.io/apis/eliq/eliq-portfolio-users-api/) — The Portfolio Users API from Eliq — 2 operation(s) for portfolio users.
- [Eliq Price Formulas API](https://apis.io/apis/eliq/eliq-price-formulas-api/) — The Price Formulas API from Eliq — 1 operation(s) for price formulas.
- [Eliq Similar Homes API](https://apis.io/apis/eliq/eliq-similar-homes-api/) — The Similar Homes API from Eliq — 3 operation(s) for similar homes.
- [Eliq User API](https://apis.io/apis/eliq/eliq-user-api/) — The User API from Eliq — 4 operation(s) for user.
- [Eliq Users API](https://apis.io/apis/eliq/eliq-users-api/) — The Users API from Eliq — 5 operation(s) for users.
- [Eliq .well Known API](https://apis.io/apis/eliq/eliq-well-known-api/) — The .well Known API from Eliq — 2 operation(s) for .well known.
- [Eliq OAUTH API](https://apis.io/apis/eliq/eliq-oauth-api/) — The Oauth API from Eliq — 1 operation(s) for oauth.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (2)

Event-driven and webhook contracts.

- [Eliq Notifications (webhooks)](https://apis.io/asyncapis/eliq/eliq-notifications-asyncapi/)
- [Eliq Webhooks](https://apis.io/asyncapis/eliq/eliq-webhooks/)

#### Event channels (1)

Individual events and webhooks the provider emits.

- [/](https://apis.io/channels/eliq/notifications/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [eliq-mcp.yml](https://apis.io/servers/eliq/eliq-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Eliq Agentic Access](https://apis.io/agentic-access/eliq/eliq-agentic-access/)

#### JSON Schema (75)

The data models the API reads and writes.

- [AcceptedResult](https://apis.io/schemas/eliq/eliq-accepted-result/)
- [Advice](https://apis.io/schemas/eliq/eliq-advice/)
- [AdvicePatchInput](https://apis.io/schemas/eliq/eliq-advice-patch-input/)
- [Anomaly](https://apis.io/schemas/eliq/eliq-anomaly/)
- [AuthInfoResult](https://apis.io/schemas/eliq/eliq-auth-info-result/)
- [Budget](https://apis.io/schemas/eliq/eliq-budget/)
- [BudgetHistory](https://apis.io/schemas/eliq/eliq-budget-history/)
- [Connection](https://apis.io/schemas/eliq/eliq-connection/)
- [ConnectionEntity](https://apis.io/schemas/eliq/eliq-connection-entity/)
- [ConnectionMetaData](https://apis.io/schemas/eliq/eliq-connection-meta-data/)
- [Consent](https://apis.io/schemas/eliq/eliq-consent/)
- [DashboardEmbedTokenResult](https://apis.io/schemas/eliq/eliq-dashboard-embed-token-result/)
- [DeviceMaxDemand](https://apis.io/schemas/eliq/eliq-device-max-demand/)
- [DeviceMaxDemandLimit](https://apis.io/schemas/eliq/eliq-device-max-demand-limit/)
- [EliqConnectUriResponse](https://apis.io/schemas/eliq/eliq-eliq-connect-uri-response/)
- [EnergyDailyData](https://apis.io/schemas/eliq/eliq-energy-daily-data/)
- [EnergyHighResolutionData](https://apis.io/schemas/eliq/eliq-energy-high-resolution-data/)
- [EnergyMonthlyData](https://apis.io/schemas/eliq/eliq-energy-monthly-data/)
- [EpcRatingResponse](https://apis.io/schemas/eliq/eliq-epc-rating-response/)
- [EUC](https://apis.io/schemas/eliq/eliq-euc/)
- [ExportJob](https://apis.io/schemas/eliq/eliq-export-job/)
- [FilterRequest](https://apis.io/schemas/eliq/eliq-filter-request/)
- [FilterResponse](https://apis.io/schemas/eliq/eliq-filter-response/)
- [HomeprofileOptions](https://apis.io/schemas/eliq/eliq-home-profile-option/)
- [HomeProfileProperty](https://apis.io/schemas/eliq/eliq-home-profile-property/)
- …and 50 more published on APIs.io

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Eliq Context](https://apis.io/jsonld/eliq/eliq-context/)

#### Overlays (4)

OpenAPI overlays, including conversational phrasing for each operation.

- [Eliq Auth Api Overlay](https://apis.io/overlays/eliq/eliq-auth-api-overlay/)
- [Eliq Data Management Api Overlay](https://apis.io/overlays/eliq/eliq-data-management-api-overlay/)
- [Eliq Insights Api Overlay](https://apis.io/overlays/eliq/eliq-insights-api-overlay/)
- [Eliq Intelligence Api Overlay](https://apis.io/overlays/eliq/eliq-intelligence-api-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Eliq API Rules](https://apis.io/rules/eliq/eliq-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Eliq Authentication](https://apis.io/security/eliq/eliq-authentication/)
- [Eliq Domain Security](https://apis.io/security/eliq/eliq-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Eliq Scopes](https://apis.io/scopes/eliq/eliq-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Eliq Plans Pricing](https://apis.io/plans/eliq/eliq-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Eliq Rate Limits](https://apis.io/rate-limits/eliq/eliq-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Eliq Finops](https://apis.io/finops/eliq/eliq-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://eliq.com)
- [Documentation](https://developer.eliq.com/docs)
- [Getting started](https://developer.eliq.com/docs/getting-started)
- [API reference](https://developer.eliq.com/api-reference)
- [Sign up](https://developer.eliq.com/create-account)
- [Support](https://www.eliq.com/contact)
- [Blog](https://www.eliq.com/learn/blog)
- [Terms of service](https://www.eliq.com/terms-of-service)
- [Privacy policy](https://www.eliq.com/privacy-policy)
- [GitHub](https://github.com/GetEliq)

## API Evangelist rating

**Kin Score 66.5** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 70.7 |
| Contract governance | 35.6 |
| Operational transparency | 65.8 |
| Developer ergonomics | 73.2 |
| Access clarity | 34.2 |

**Agent readiness 47.4** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 45.1** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/eliq/](https://apis.io/providers/eliq/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Eliq: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/eliq/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
