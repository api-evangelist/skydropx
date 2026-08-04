# Skydropx (skydropx)

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

Skydropx is a Mexican multi-carrier shipping and logistics platform that lets e-commerce sellers and businesses compare rates, generate labels, schedule pickups, and track parcels across national and international carriers from a single API.

## Access Model (Honest Summary)

Skydropx is a proprietary SaaS platform (not open source). There are effectively three documented public REST surfaces, all request/response over HTTPS:

- **Skydropx Pro API** — base `https://pro.skydropx.com/api/v1` (sandbox `https://sb-pro.skydropx.com/api/v1`). Authenticated with an **OAuth2 client-credentials Bearer token** obtained from `POST /oauth/token` using your `client_id` and `client_secret`. Tokens last about two hours; requests are rate limited to roughly two per second. This is the surface modeled in `openapi/skydropx-openapi.yml` and the collections.
- **Classic Skydropx API** — base `https://api.skydropx.com/v1`. Authenticated with an **API key** passed as `Authorization: Token token=YOUR_API_KEY` (keys issued by Skydropx support on request). Documented but not modeled here.
- **Radar tracking API** — base `https://radar-api.skydropx.com/v1`. Shipments and tracking. Documented but not modeled here.

Billing is **prepaid pay-per-label**: the platform and API are free to use, and you are charged the cost of each label (plus carrier surcharges) from a wallet balance readable via `GET /finance/credits`.

**Grounding note:** base URLs, the OAuth2 flow, the token endpoint, the ~2 req/sec rate limit, and the resource paths are grounded in Skydropx's public documentation. Request/response **schemas** in the OpenAPI are **modeled** from documented fields and common shipping-API conventions and should be reconciled against the live reference before production use. There is **no documented public WebSocket (`wss://`) API**; asynchronous shipment status updates are delivered to client **webhook** endpoints via HTTP POST.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/skydropx/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/skydropx/refs/heads/main/apis.yml)

## Tags

- Shipping
- Logistics
- Multi-Carrier
- Mexico
- Latin America
- Labels
- Rates
- Parcels
- Tracking
- Fulfillment
- SaaS

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### Skydropx Quotations API

Request multi-carrier shipping rates for a parcel between an origin and destination. A quotation returns available carrier services with prices and delivery estimates; the chosen rate is then used to create a shipment.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Quotations
- Rates
- Carriers

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Shipments API

Create shipments from a quotation and rate, list and retrieve shipments, cancel shipments, and add shipment protection. Creating a shipment purchases the label and debits the account wallet balance.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Shipments
- Labels
- Fulfillment

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Orders and Labels API

Create, list, retrieve, and update orders, and fetch the generated shipping label URLs (PDF) for an order. Printing formats can be configured per account.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Orders
- Labels
- Printing

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Pickups API

Schedule, list, retrieve, and reschedule carrier pickups (recolecciones) for created shipments, and check pickup date availability by coverage.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Pickups
- Recolecciones
- Scheduling

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Address Templates API

Manage reusable saved addresses - create, list, get, update, and delete address templates, and validate an address against carrier serviceability.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Addresses
- Templates
- Validation

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Tracking API

Track a shipment by tracking number and report tracking events for fleet/external shipments. Status changes (created, picked up, in transit, delivered, exception) are also delivered to client webhook endpoints.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Tracking
- Status
- Webhooks

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Finance API

Check the prepaid account credit balance and list extra charges / surcharges applied to shipments, supporting reconciliation of pay-per-label spend.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Finance
- Credits
- Billing

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Skydropx Catalog API

Read reference catalogs used to build shipments - available carrier services, packaging type codes, office/drop-off points, and SAT Carta Porte consignment-note codes required for Mexican shipping.

- **Human URL:** [https://pro.skydropx.com/es-MX/api-docs](https://pro.skydropx.com/es-MX/api-docs)
- **Base URL:** `https://pro.skydropx.com/api/v1`

#### Tags

- Carriers
- Packagings
- Consignment Notes

#### Properties

- [Documentation](https://docs.skydropx.com/)
- [API Reference](https://pro.skydropx.com/es-MX/api-docs)
- [OpenAPI](openapi/skydropx-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/skydropx.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/skydropx.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Domain Security](security/skydropx-domain-security.yml)
- [Authentication](authentication/skydropx-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/skydropx)
- [Website](https://www.skydropx.com/)
- [Documentation](https://docs.skydropx.com/)
- [Plans](plans/skydropx-plans-pricing.yml)
- [Rate Limits](rate-limits/skydropx-rate-limits.yml)
- [Fin Ops](finops/skydropx-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
