# Eliq (eliq)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Eliq provides energy data and analytics APIs for utilities and energy app developers. The platform combines a decade of analytics and machine learning trained on millions of homes to deliver consumption insights, disaggregation, forecasting, peak detection, tariff comparison, and customer segmentation.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/eliq/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags:

 - Energy, Utilities, Analytics, Sustainability

## Timestamps

- **Created:** 2025-05-02
- **Modified:** 2026-04-28

## APIs

### Eliq Auth API
The Eliq Auth API authenticates client applications and issues access tokens used to call the Insights, Data Management, and Intelligence APIs. It supports the credential flows required for utility-side integrations.

**Human URL:** [https://developer.eliq.com/api-reference](https://developer.eliq.com/api-reference)

#### Tags:

 - Authentication, Energy

#### Properties

- [Documentation](https://developer.eliq.com/api-reference)
- [DeveloperPortal](https://developer.eliq.com)

### Eliq Data Management API
The Eliq Data Management API ingests and manages customer, location, and meter data inside the Eliq system. Clients use it to provision users and locations, post energy consumption readings, attach metadata such as tariffs and dwelling information, and keep the dataset that powers the Insights API up to date.

**Human URL:** [https://developer.eliq.com/doc/eliq-apis](https://developer.eliq.com/doc/eliq-apis)

#### Tags:

 - Data Management, Energy, Utilities

#### Properties

- [Documentation](https://developer.eliq.com/doc/eliq-apis)

### Eliq Insights API
The Eliq Insights API delivers analytics and presentation-ready data for end-user energy applications. It exposes consumption aggregates by day, week, month, and year, trends, cost, CO2 footprint, day-ahead pricing, weather, peak power, tariff comparisons, PV disaggregation, forecasting, anomalies, and budget or goal tracking. Device-specific energy insights use NILM disaggregation to attribute consumption to appliances.

**Human URL:** [https://developer.eliq.com/doc/energy-insights-for-businesses](https://developer.eliq.com/doc/energy-insights-for-businesses)

#### Tags:

 - Insights, Analytics, Energy, Utilities, Disaggregation

#### Properties

- [Documentation](https://developer.eliq.com/doc/energy-insights-for-businesses)
- [Documentation](https://developer.eliq.com/doc/device-specific-energy-insights)

### Eliq Intelligence API
The Eliq Intelligence API provides customer-level analytics designed for utility service, operations, and growth teams. It supports customer segmentation, behavioral classification, and personalized recommendations derived from consumption history, weather, tariffs, and disaggregation models. Access to the Intelligence API is granted on request.

**Human URL:** [https://developer.eliq.com/api-reference](https://developer.eliq.com/api-reference)

#### Tags:

 - Intelligence, Segmentation, Energy, Utilities

#### Properties

- [Documentation](https://developer.eliq.com/api-reference)

## Common Properties

- [Website](https://eliq.com)
- [DeveloperPortal](https://developer.eliq.com)
- [Documentation](https://developer.eliq.com/docs)
- [Documentation](https://eliq.com/api/)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
