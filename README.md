# Skydropx

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

Skydropx is a Mexican multi-carrier shipping and logistics platform that lets e-commerce sellers and businesses compare rates, generate labels, schedule pickups, and track parcels across national and international carriers from a single API. Its modern Skydropx Pro API (base https://pro.skydropx.com/api/v1) is a REST interface secured with OAuth2 client-credentials Bearer tokens and covers quotations, shipments, labels/orders, pickups, address templates, tracking, and account credit balances. A separate classic Skydropx API (https://api.skydropx.com/v1, authenticated with an API key Token header) and a Radar tracking API also exist. Billing is prepaid - the platform is free to use and you pay per label from a wallet balance.

**Areas:** Shipping · Logistics · Multi-Carrier · Mexico · Latin America · Labels · Rates · Parcel · Tracking · Fulfillment · Software-as-a-Service

## Skydropx on APIs.io

Everything profiled for Skydropx is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/skydropx/](https://apis.io/providers/skydropx/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Skydropx Address Templates API](https://apis.io/apis/skydropx/skydropx-address-templates-api/) — Reusable saved addresses and carrier validation.
- [Skydropx Authentication API](https://apis.io/apis/skydropx/skydropx-authentication-api/) — OAuth2 client-credentials token issuance.
- [Skydropx Catalog API](https://apis.io/apis/skydropx/skydropx-catalog-api/) — Carrier services, packagings, and consignment-note codes.
- [Skydropx Finance API](https://apis.io/apis/skydropx/skydropx-finance-api/) — Prepaid credit balance and extra charges.
- [Skydropx Orders and Labels API](https://apis.io/apis/skydropx/skydropx-orders-and-labels-api/) — Orders and their generated shipping label URLs.
- [Skydropx Pickups API](https://apis.io/apis/skydropx/skydropx-pickups-api/) — Schedule and manage carrier pickups (recolecciones).
- [Skydropx Quotations API](https://apis.io/apis/skydropx/skydropx-quotations-api/) — Multi-carrier rate quotations for a parcel.
- [Skydropx Shipments API](https://apis.io/apis/skydropx/skydropx-shipments-api/) — Create, list, retrieve, cancel, and protect shipments.
- [Skydropx Tracking API](https://apis.io/apis/skydropx/skydropx-tracking-api/) — Track shipments and report tracking events.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [skydropx](https://apis.io/servers/skydropx/skydropx/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Skydropx Agentic Access](https://apis.io/agentic-access/skydropx/skydropx-agentic-access/)

#### Collections (10)

Postman and Open Collection request collections.

- [Skydropx Pro API](https://apis.io/collections/skydropx/open-skydropx/)
- [Skydropx Pro Address Templates API](https://apis.io/collections/skydropx/open-skydropx-address-templates-api/)
- [Skydropx Pro Address Templates Authentication API](https://apis.io/collections/skydropx/open-skydropx-authentication-api/)
- [Skydropx Pro Address Templates Catalog API](https://apis.io/collections/skydropx/open-skydropx-catalog-api/)
- [Skydropx Pro Address Templates Finance API](https://apis.io/collections/skydropx/open-skydropx-finance-api/)
- [Skydropx Pro Address Templates Orders and Labels API](https://apis.io/collections/skydropx/open-skydropx-orders-and-labels-api/)
- [Skydropx Pro Address Templates Pickups API](https://apis.io/collections/skydropx/open-skydropx-pickups-api/)
- [Skydropx Pro Address Templates Quotations API](https://apis.io/collections/skydropx/open-skydropx-quotations-api/)
- [Skydropx Pro Address Templates Shipments API](https://apis.io/collections/skydropx/open-skydropx-shipments-api/)
- [Skydropx Pro Address Templates Tracking API](https://apis.io/collections/skydropx/open-skydropx-tracking-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Skydropx Authentication](https://apis.io/security/skydropx/skydropx-authentication/)
- [Skydropx Domain Security](https://apis.io/security/skydropx/skydropx-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Skydropx Plans Pricing](https://apis.io/plans/skydropx/skydropx-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Skydropx Rate Limits](https://apis.io/rate-limits/skydropx/skydropx-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Skydropx Finops](https://apis.io/finops/skydropx/skydropx-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.skydropx.com/)
- [Documentation](https://docs.skydropx.com/)

## API Evangelist rating

**Kin Score 24.8** — emerging · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 49.7 |
| Contract governance | 0.0 |
| Operational transparency | 7.9 |
| Developer ergonomics | 28.6 |
| Access clarity | 5.3 |

**Agent readiness 44.1** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 10.0** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/skydropx/](https://apis.io/providers/skydropx/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Skydropx: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/skydropx/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
