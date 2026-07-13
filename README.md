# Skydropx (skydropx)

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
