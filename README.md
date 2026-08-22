# Bargo Congress Trades API (bargo-congress-trades-api)

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

A free JSON REST API and hosted MCP server from Bargo that normalizes U.S. House and Senate STOCK Act securities transaction disclosures into a queryable dataset — currently 42,000+ disclosed trades across 415 members and 4,100+ tickers. Six read-only GET operations cover trades (filterable by ticker, member, chamber, transaction type and date range), a member roster, per-member disclosure histories, aggregate statistics, and a dataset-freshness health check. Unusually for a free congressional-trading tracker, every row carries per-trade price performance — estimated price at the trade, latest price, and percent move since. Records are parsed and deduplicated from the official U.S. House Clerk Financial Disclosure reports and Senate eFD Periodic Transaction Reports, so disclosures lag transactions by up to ~45 days. Access is anonymous by default at a lower quota; a free no-card API key raises limits and unlocks a focused three-tool MCP server for agents. Open CORS, an embeddable browser widget, and first-party JavaScript and Python clients. Attribution is required; bulk redistribution of raw records is not permitted.

**APIs.json:** [https://bargo-congress-trades-api.apievangelist.com/apis.yml](https://bargo-congress-trades-api.apievangelist.com/apis.yml)

## Tags

- congress
- finance
- stocks
- government
- stock-act
- mcp
- congressional-trading
- financial-disclosure
- market-data
- public-data
- free-api
- open-data

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-08-09

## APIs

### Congress Trades MCP Server

A focused Streamable HTTP MCP server exposing three read-only tools over the Congress Trades dataset — get_congress_trades, get_congress_member and get_congress_stats. The handshake and tools/list are anonymous; tool calls require a free fak_ key via X-Api-Key, Bearer, or a token query parameter. An official Docker image bridges stdio-only MCP clients to it.

- **Human URL:** [https://www.bargo.ai/free-apis/congress](https://www.bargo.ai/free-apis/congress)
- **Base URL:** `https://www.bargo.ai/free-apis/congress/mcp`

#### Tags

- mcp
- agents
- congress
- stocks

#### Properties

- [M C P Server](mcp/bargo-congress-trades-api-mcp.yml)
- [M C P Server](https://www.bargo.ai/free-apis/congress/mcp)
- [Tool Crosswalk](mcp/bargo-congress-trades-api-tool-crosswalk.yml)
- [Agent Skill](skills/_index.yml)
- [Authentication](authentication/bargo-congress-trades-api-authentication.yml)
- [Documentation](https://github.com/bargo-ai/bargo-free-api-packages/blob/main/docs/mcp.md)
- [Postman Collection](collections/bargo-congress-trades-api-members-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bargo-congress-trades-api-members-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/bargo-congress-trades-api-statistics-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bargo-congress-trades-api-statistics-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/bargo-congress-trades-api-trades-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bargo-congress-trades-api-trades-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bargo Congress Trades API Members API

Members of Congress and their disclosure histories.

- **Human URL:** [https://www.bargo.ai/free-apis/congress](https://www.bargo.ai/free-apis/congress)
- **Base URL:** `https://www.bargo.ai/free-apis/congress/v1`

#### Tags

- Members

#### Properties

- [OpenAPI](openapi/bargo-congress-trades-api-members-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bargo-congress-trades-api-members-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bargo-congress-trades-api-members-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://www.bargo.ai/free-apis/congress)
- [API Reference](https://www.bargo.ai/free-apis/congress)
- [Authentication](authentication/bargo-congress-trades-api-authentication.yml)
- [Conventions](conventions/bargo-congress-trades-api-conventions.yml)
- [Error Catalog](errors/bargo-congress-trades-api-problem-types.yml)
- [Data Model](data-model/bargo-congress-trades-api-data-model.yml)
- [Rate Limits](rate-limits/bargo-congress-trades-api-rate-limits.yml)
- [Examples](examples/_index.yml)
- [Components](components/bargo-congress-trades-api-components.yml)
- [S D Ks](packages/bargo-congress-trades-api-packages.yml)

### Bargo Congress Trades API Statistics API

Aggregate dataset statistics and freshness.

- **Human URL:** [https://www.bargo.ai/free-apis/congress](https://www.bargo.ai/free-apis/congress)
- **Base URL:** `https://www.bargo.ai/free-apis/congress/v1`

#### Tags

- Statistics

#### Properties

- [OpenAPI](openapi/bargo-congress-trades-api-statistics-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bargo-congress-trades-api-statistics-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bargo-congress-trades-api-statistics-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://www.bargo.ai/free-apis/congress)
- [API Reference](https://www.bargo.ai/free-apis/congress)
- [Authentication](authentication/bargo-congress-trades-api-authentication.yml)
- [Conventions](conventions/bargo-congress-trades-api-conventions.yml)
- [Error Catalog](errors/bargo-congress-trades-api-problem-types.yml)
- [Data Model](data-model/bargo-congress-trades-api-data-model.yml)
- [Rate Limits](rate-limits/bargo-congress-trades-api-rate-limits.yml)
- [Examples](examples/_index.yml)
- [Components](components/bargo-congress-trades-api-components.yml)
- [S D Ks](packages/bargo-congress-trades-api-packages.yml)

### Bargo Congress Trades API Trades API

Normalized House and Senate securities transactions.

- **Human URL:** [https://www.bargo.ai/free-apis/congress](https://www.bargo.ai/free-apis/congress)
- **Base URL:** `https://www.bargo.ai/free-apis/congress/v1`

#### Tags

- Trades

#### Properties

- [OpenAPI](openapi/bargo-congress-trades-api-trades-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bargo-congress-trades-api-trades-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bargo-congress-trades-api-trades-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://www.bargo.ai/free-apis/congress)
- [API Reference](https://www.bargo.ai/free-apis/congress)
- [Authentication](authentication/bargo-congress-trades-api-authentication.yml)
- [Conventions](conventions/bargo-congress-trades-api-conventions.yml)
- [Error Catalog](errors/bargo-congress-trades-api-problem-types.yml)
- [Data Model](data-model/bargo-congress-trades-api-data-model.yml)
- [Rate Limits](rate-limits/bargo-congress-trades-api-rate-limits.yml)
- [Examples](examples/_index.yml)
- [Components](components/bargo-congress-trades-api-components.yml)
- [S D Ks](packages/bargo-congress-trades-api-packages.yml)

## Common Properties

- [Domain Security](security/bargo-congress-trades-api-domain-security.yml)
- [Agentic Access](agentic-access/bargo-congress-trades-api-agentic-access.yml)
- [Authentication](authentication/bargo-congress-trades-api-authentication.yml)
- [Developer Portal](https://www.bargo.ai/free-apis/congress)
- [Documentation](https://www.bargo.ai/free-apis/congress)
- [API Reference](https://www.bargo.ai/free-apis/congress/openapi.json)
- [Getting Started](https://www.bargo.ai/free-apis/congress)
- [Sign Up](https://www.bargo.ai/free-apis/dash)
- [Support](https://www.bargo.ai/contact)
- [Terms of Service](https://www.bargo.ai/free-apis/terms)
- [Privacy Policy](https://www.bargo.ai/privacy)
- [GitHub Organization](https://github.com/bargo-ai)
- [Blog](https://www.bargo.ai/research)
- [M C P Server](mcp/bargo-congress-trades-api-mcp.yml)
- [Tool Crosswalk](mcp/bargo-congress-trades-api-tool-crosswalk.yml)
- [Agent Skill](skills/_index.yml)
- [L L Ms Txt](llms/bargo-congress-trades-api-llms.txt)
- [Well Known](well-known/bargo-congress-trades-api-well-known.yml)
- [Packages](packages/bargo-congress-trades-api-packages.yml)
- [S D Ks](packages/bargo-congress-trades-api-packages.yml)
- [Conventions](conventions/bargo-congress-trades-api-conventions.yml)
- [Error Catalog](errors/bargo-congress-trades-api-problem-types.yml)
- [Data Model](data-model/bargo-congress-trades-api-data-model.yml)
- [Rate Limits](rate-limits/bargo-congress-trades-api-rate-limits.yml)
- [Lifecycle](lifecycle/bargo-congress-trades-api-lifecycle.yml)
- [Conformance](conformance/bargo-congress-trades-api-conformance.yml)
- [Components](components/bargo-congress-trades-api-components.yml)
- [Examples](examples/_index.yml)
- [Overlay](overlays/bargo-congress-trades-api-congress-trades-overlay.yaml)

## Maintainers

**FN:** Bargo
**Email:** support@bargo.ai
**URL:** https://www.bargo.ai/
