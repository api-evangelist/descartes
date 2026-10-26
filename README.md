# Descartes Systems Group (descartes)

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

The Descartes Systems Group is a global logistics and supply chain software company whose cloud-based Global Logistics Network connects manufacturers, distributors, carriers, brokers, and freight forwarders. Descartes delivers its capabilities across a large family of products - real-time freight visibility and carrier sourcing (Descartes MacroPoint), customs and regulatory compliance and trade content (Descartes CustomsInfo, NetCHB), global trade intelligence (Descartes Datamyne), routing and mobile, and B2B connectivity and messaging.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/descartes/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/descartes/refs/heads/main/apis.yml)

## Access Model (Read This First)

Descartes exposes APIs **per-product**, and access is **customer/partner-gated rather than open self-service**:

- The **MacroPoint** APIs (Visibility, Capacity, Carrier) are publicly documented at `docs.macropoint.com`, `capacitydocs.macropoint.com`, and `carrierdocs.macropoint.com`, with a public `macropoint-telematics` Postman workspace - but calling them requires **MacroPoint customer credentials** (HTTP Basic auth). The Visibility API is XML over HTTPS at base `https://macropoint-lite.com/api/1.0`.
- **CustomsInfo Trade Content** and **Datamyne Global Trade Data** APIs are arranged via **subscription/contract**; there is no public self-service endpoint reference.
- The **Descartes API portal** at `api.descartes.com` lets developers browse APIs and **sign up/request approval to acquire keys** for B2B connectivity and other product APIs.

Where a full endpoint surface is not publicly published, this entry **models** the operations from Descartes' own documentation and product materials and flags them as `endpointsModeled` rather than fabricating specific paths. Only the MacroPoint Visibility `createorder` and `location` operations are listed as confirmed.

Pricing is **enterprise / contact-sales**; no public per-call price list is published.

## Tags

- Logistics
- Supply Chain
- Freight Visibility
- Shipment Tracking
- Customs Compliance
- Global Trade
- Trade Content
- Carrier Sourcing

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Descartes MacroPoint Visibility API

Real-time freight and shipment visibility. Create, update, monitor, and stop tracking sessions on loads from a TMS/ERP and receive location, order-status, trip-event, and form-submit updates via HTTP callbacks. Base `https://macropoint-lite.com/api/1.0`, HTTP Basic auth, XML bodies. Confirmed: `POST /orders/createorder`, `POST /tms/data/location`.

- **Documentation:** [https://docs.macropoint.com/](https://docs.macropoint.com/)
- **Base URL:** `https://macropoint-lite.com/api/1.0`

### Descartes MacroPoint Capacity Integration API

Intelligent carrier sourcing and capacity matching. An Import API pushes capacity/load data into MacroPoint Capacity; an Export API returns carrier matches. Documented at `capacitydocs.macropoint.com`. Operations modeled (`endpointsModeled`); access gated behind a Capacity account.

- **Documentation:** [https://capacitydocs.macropoint.com/](https://capacitydocs.macropoint.com/)

### Descartes MacroPoint Carrier Integration API

Carrier-facing integration for the Visibility network. Carriers and telematics/ELD providers supply location updates (lat/long or address), load event updates (arrival/departure), and tracking-method assignment. Documented at `carrierdocs.macropoint.com` with public Postman collections. Operations modeled (`endpointsModeled`); requires carrier/partner onboarding.

- **Documentation:** [https://carrierdocs.macropoint.com/](https://carrierdocs.macropoint.com/)

### Descartes CustomsInfo Trade Content API

Trade content and classification for customs and regulatory compliance - HS codes, tariff/duty rates, binding rulings, import/export restrictions, licensing and origin data, in JSON or XML for embedding in ERP/GTM/WMS/TMS. Operations modeled (`endpointsModeled`); access via contract with a Descartes trade content specialist.

- **Documentation:** [https://www.customsinfo.com/knowledge-center/trade-content-apis-streamlining-classification-and-enhancing-business-integration/](https://www.customsinfo.com/knowledge-center/trade-content-apis-streamlining-classification-and-enhancing-business-integration/)

### Descartes Datamyne Global Trade Data API

Programmatic access to Descartes Datamyne's global import/export trade data - bill-of-lading and customs records, trade flows, and company/commodity intelligence. Operations modeled (`endpointsModeled`); access via subscription/contract.

- **Documentation:** [https://www.datamyne.com/our-product/global-trade-data-api/](https://www.datamyne.com/our-product/global-trade-data-api/)

### Descartes B2B API Connectivity

Real-time B2B connectivity over the Global Logistics Network, complementing EDI. Synchronous request/response for marketplace connectivity (listings, orders, payments, reports with retailers such as Amazon and bol.com) and multimodal carrier connectivity (rates, shipments, bookings, waybills). APIs discovered and keys acquired via the Descartes API portal. Operations modeled (`endpointsModeled`).

- **Developer Portal:** [https://api.descartes.com/](https://api.descartes.com/)

## Common Properties

- [Website](https://www.descartes.com)
- [Developer Portal](https://api.descartes.com/)
- [Documentation](https://docs.macropoint.com/)
- [LinkedIn](https://www.linkedin.com/company/descartes-systems-group)
- [Postman Workspace](https://www.postman.com/macropoint-telematics)
- [Plans](plans/descartes-plans-pricing.yml)
- [Rate Limits](rate-limits/descartes-rate-limits.yml)
- [Fin Ops](finops/descartes-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
