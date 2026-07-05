# Descartes Systems Group (descartes)

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
