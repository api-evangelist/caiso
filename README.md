# California ISO (caiso)

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

The California Independent System Operator (CAISO) is the non-profit public benefit corporation that operates the high-voltage transmission grid serving roughly 80 percent of California plus a portion of Nevada, and runs the wholesale day-ahead and real-time electricity markets, the Western Energy Imbalance Market (WEIM), and the Extended Day-Ahead Market (EDAM). As a system and market operator in the United States it sits at the wholesale layer of the energy value chain — upstream of the investor-owned utilities that bill retail customers, and therefore it holds no retail customer accounts and publishes no consumer usage data. Its API posture is a clean split: market data is genuinely open and consumer data does not exist.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/caiso/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/caiso/refs/heads/main/apis.yml)

## Tags

- Energy
- United States
- Electricity
- Energy Markets
- Grid
- Renewables
- System Operator
- Market Data
- California

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### CAISO OASIS Download API

The Open Access Same-time Information System (OASIS) Download API — CAISO's public wholesale market data interface. Two servlets, SingleZip and GroupZip, accept a `queryname` or `groupid` plus a UTC datetime range and return a ZIP containing CIM-format XML (`resultformat=5`) or CSV (`resultformat=6`). Report families cover locational marginal prices (`PRC_LMP`, `PRC_INTVL_LMP`, `PRC_CURR_LMP`), system load and renewables forecasts (`SLD_FCST`, `SLD_REN_FCST`), ancillary services, congestion revenue rights, and the ATLAS reference data set (`ATL_PNODE` and friends). Requests are anonymous — no API key, token, or account.

- **Human URL:** [https://www.caiso.com/systems-applications/developer-portal](https://www.caiso.com/systems-applications/developer-portal)
- **Base URL:** `https://oasis.caiso.com/oasisapi`

#### Tags

- Energy Markets
- Electricity
- Market Data
- Pricing
- Forecasting
- Grid

#### Properties

- [Documentation](https://www.caiso.com/documents/oasis-frequently-asked-questions.pdf) — OASIS Frequently Asked Questions
- [Documentation](https://www.caiso.com/documents/oasisapispecification.pdf) — Interface Specification for OASIS
- [Documentation](https://www.caiso.com/systems-applications/developer-portal)
- [Sign Up](https://developer.caiso.com/_login/developersignup.aspx)
- [Portal](https://oasis.caiso.com/mrioasis/logon.do)

### CAISO Today's Outlook Data Feeds

The CSV feeds behind CAISO's public Today's Outlook dashboard. Anonymous GET requests to `https://www.caiso.com/outlook/current/{report}.csv` return the current operating day at five-minute resolution, and `https://www.caiso.com/outlook/history/{YYYYMMDD}/{report}.csv` returns a past day. Confirmed reports are `fuelsource`, `demand`, `netdemand`, and `co2`. CAISO notes these are telemetry-based summaries and will not tie out to the market-based numbers in OASIS.

- **Human URL:** [https://www.caiso.com/todays-outlook](https://www.caiso.com/todays-outlook)
- **Base URL:** `https://www.caiso.com/outlook`

#### Tags

- Grid
- Renewables
- Carbon
- Electricity
- Market Data

#### Properties

- [Documentation](https://www.caiso.com/todays-outlook)
- [Documentation](https://www.caiso.com/todays-outlook/supply)
- [Documentation](https://www.caiso.com/todays-outlook/emissions)

## Common Properties

- [Website](https://www.caiso.com/)
- [Developer Portal](https://developer.caiso.com/)
- [Documentation](https://www.caiso.com/systems-applications/developer-portal)
- [Sign Up](https://developer.caiso.com/_login/developersignup.aspx)
- [Authentication](https://www.caiso.com/systems-applications/requesting-access-certificates)
- [Portal](https://www.caiso.com/systems-applications/portals-applications)
- [Support](https://caiso.my.site.com/custsvccomm/s/knowledge-articles)
- [Documentation](https://www.caiso.com/library/business-practice-manuals)
- [Blog](https://www.caiso.com/about/news)

## Mandate and Access Posture

- **Mandate regime:** `other` — US federal open-access wholesale transparency (FERC Order Nos. 888/889 OASIS requirement), **not** a consumer data right.
- **Mandate status:** `live-implemented` — verified by anonymous `curl` against `https://oasis.caiso.com/oasisapi/SingleZip` on 2026-07-27, which returned HTTP 200 and a ZIP containing real day-ahead LMP CSV rows. Five further query names were confirmed the same way.
- **Data standard:** IEC CIM-derived XML for OASIS payloads (per the OASIS interface specification), with a CSV alternative; query and report vocabulary is proprietary to CAISO. No Green Button / ESPI reference found anywhere.
- **Consumer data API:** none, and none possible — CAISO has no retail customers.
- **Market data open:** yes — OASIS plus the Today's Outlook CSV feeds, both fully anonymous.
- **Access gate:** `self-serve` for the API surface (literally no credential of any kind). The *documentation* is `application-approval`: CAISO's OASIS FAQ states developer-site signup requires a recognized corporate email domain and a detailed justification, and consumer email domains "would be subject to rejection." Every other CAISO system is `partner-only` behind a company User Access Administrator plus PKI client certificates.
- **Auth model:** none for OASIS and Today's Outlook; forms-based SharePoint login for the developer documentation site; X.509 client certificates chained to the CAISO issuing authority plus UAA-sponsored accounts for participant systems. No OpenID Connect discovery document is served.
- **Machine-readable contracts:** none published. No OpenAPI, AsyncAPI, Postman collection, or GraphQL schema was found, so no `openapi/` directory exists in this repo.

See [`review.yml`](review.yml) for the full probe log with HTTP status for every URL tested.
