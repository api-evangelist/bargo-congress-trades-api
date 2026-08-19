# Bargo Congress Trades API (bargo-congress-trades-api)

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
