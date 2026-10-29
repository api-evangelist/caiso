# California ISO

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

The California Independent System Operator (CAISO) is the non-profit public benefit corporation that operates the high-voltage transmission grid serving roughly 80 percent of California plus a portion of Nevada, and runs the wholesale day-ahead and real-time electricity markets, the Western Energy Imbalance Market (WEIM), and the Extended Day-Ahead Market (EDAM). As a system and market operator in the United States it sits at the wholesale layer of the energy value chain — upstream of the investor-owned utilities that bill retail customers, and therefore it holds no retail customer accounts and publishes no consumer usage data. Its API posture is a clean split: market data is genuinely open and consumer data does not exist. The OASIS Download API at https://oasis.caiso.com/oasisapi serves locational marginal prices, demand and renewables forecasts, ancillary services, transmission and nodal reference data as zipped CSV or CIM XML to anonymous callers with no key, no account and no registration — CAISO states in writing that every system it operates except OASIS requires a company User Access Administrator to grant access. The Today's Outlook telemetry feeds under https://www.caiso.com/outlook publish five-minute fuel mix, demand, net demand and CO2 as plain CSV, also anonymously. Everything else — market submission, dispatch, settlements and the participant portals — is behind PKI client certificates and UAA-sponsored accounts, and even the OASIS reference documentation on the developer site requires a signup reviewed against a corporate email domain and a written justification. No Green Button, ESPI, or Consumer Data Right surface exists here and none is expected to; the obligation CAISO answers to is FERC's open-access transparency regime, not a consumer data right. No OpenAPI, AsyncAPI, or other machine-readable contract is published for any of it.

**Areas:** Energy · United States · Electricity · Energy Markets · Grid · Renewables · System Operator · Market Data · California

## California ISO on APIs.io

Everything profiled for California ISO is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/caiso/](https://apis.io/providers/caiso/)** — or go straight to one of the APIs or properties below.

### APIs (2)

- [CAISO OASIS Download API](https://apis.io/apis/caiso/caiso-oasis-download-api/) — The Open Access Same-time Information System (OASIS) Download API — CAISO's public wholesale market data interface. Two servlets, SingleZip and GroupZip,…
- [CAISO Today's Outlook Data Feeds](https://apis.io/apis/caiso/caiso-todays-outlook-data-feeds/) — The CSV feeds behind CAISO's public Today's Outlook dashboard. Anonymous GET requests to https://www.caiso.com/outlook/current/{report}.csv return the…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Caiso Authentication](https://apis.io/security/caiso/caiso-authentication/)
- [Caiso Domain Security](https://apis.io/security/caiso/caiso-domain-security/)

#### Rate limits (1)

Published request limits.

- [Caiso Rate Limits](https://apis.io/rate-limits/caiso/caiso-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.caiso.com/)
- [Documentation](https://www.caiso.com/systems-applications/developer-portal)
- [Getting started](https://www.caiso.com/getting-started)
- [API reference](https://www.caiso.com/documents/oasisapispecification.pdf)
- [Sign up](https://developer.caiso.com/_login/developersignup.aspx)
- [Support](https://caiso.my.site.com/custsvccomm/s/knowledge-articles)
- [Blog](https://www.caiso.com/about/news)
- [Terms of service](https://www.caiso.com/privacy-terms-of-use#api-terms-of-use)
- [Privacy policy](https://www.caiso.com/privacy-terms-of-use)

## API Evangelist rating

**Kin Score 36.8** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 6.5 |
| Contract governance | 19.7 |
| Operational transparency | 52.6 |
| Developer ergonomics | 57.1 |
| Access clarity | 34.2 |

**Agent readiness 9.2** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 20.5** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/caiso/](https://apis.io/providers/caiso/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for California ISO: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/caiso/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
