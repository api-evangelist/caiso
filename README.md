# California ISO (caiso)

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
