# Bargo Congress Trades API

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

**Areas:** Congress · Finance · Stocks · Government · stock-act · MCP · Congressional Trading · financial-disclosure · Market Data · Public Data · Free API · Open Data

## Bargo Congress Trades API on APIs.io

Everything profiled for Bargo Congress Trades API is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/bargo-congress-trades-api/](https://apis.io/providers/bargo-congress-trades-api/)** — or go straight to one of the APIs or properties below.

### APIs (4)

- [Congress Trades MCP Server](https://apis.io/apis/bargo-congress-trades-api/congress-trades-mcp-server/) — A focused Streamable HTTP MCP server exposing three read-only tools over the Congress Trades dataset — get_congress_trades, get_congress_member and…
- [Bargo Congress Trades API Members API](https://apis.io/apis/bargo-congress-trades-api/bargo-congress-trades-api-members-api/) — Members of Congress and their disclosure histories.
- [Bargo Congress Trades API Statistics API](https://apis.io/apis/bargo-congress-trades-api/bargo-congress-trades-api-statistics-api/) — Aggregate dataset statistics and freshness.
- [Bargo Congress Trades API Trades API](https://apis.io/apis/bargo-congress-trades-api/bargo-congress-trades-api-trades-api/) — Normalized House and Senate securities transactions.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [bargo-congress](https://apis.io/servers/bargo-congress-trades-api/bargo-congress/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Bargo Congress Trades Api Agentic Access](https://apis.io/agentic-access/bargo-congress-trades-api/bargo-congress-trades-api-agentic-access/)

#### Examples (3)

Example requests and responses.

- [Bargo Congress Trades Api Get Health Example](https://apis.io/examples/bargo-congress-trades-api/bargo-congress-trades-api-get-health-example/)
- [Bargo Congress Trades Api Get Stats Example](https://apis.io/examples/bargo-congress-trades-api/bargo-congress-trades-api-get-stats-example/)
- [Bargo Congress Trades Api List Trades By Ticker Example](https://apis.io/examples/bargo-congress-trades-api/bargo-congress-trades-api-list-trades-by-ticker-example/)

#### Collections (3)

Postman and Open Collection request collections.

- [Bargo Congress Trades Members API](https://apis.io/collections/bargo-congress-trades-api/open-bargo-congress-trades-api-members-api/)
- [Bargo Congress Trades Statistics API](https://apis.io/collections/bargo-congress-trades-api/open-bargo-congress-trades-api-statistics-api/)
- [Bargo Congress Trades API](https://apis.io/collections/bargo-congress-trades-api/open-bargo-congress-trades-api-trades-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Bargo Congress Trades Api Congress Trades Overlay](https://apis.io/overlays/bargo-congress-trades-api/bargo-congress-trades-api-congress-trades-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Bargo Congress Trades Api Authentication](https://apis.io/security/bargo-congress-trades-api/bargo-congress-trades-api-authentication/)
- [Bargo Congress Trades Api Domain Security](https://apis.io/security/bargo-congress-trades-api/bargo-congress-trades-api-domain-security/)

#### Rate limits (1)

Published request limits.

- [Bargo Congress Trades Api Rate Limits](https://apis.io/rate-limits/bargo-congress-trades-api/bargo-congress-trades-api-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.bargo.ai/)
- [Documentation](https://www.bargo.ai/free-apis/congress)
- [Getting started](https://www.bargo.ai/free-apis/congress)
- [API reference](https://www.bargo.ai/free-apis/congress/openapi.json)
- [Sign up](https://www.bargo.ai/free-apis/dash)
- [Support](https://www.bargo.ai/contact)
- [Blog](https://www.bargo.ai/research)
- [Terms of service](https://www.bargo.ai/free-apis/terms)
- [Privacy policy](https://www.bargo.ai/privacy)
- [GitHub](https://github.com/bargo-ai)

## API Evangelist rating

**Kin Score 48.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 51.7 |
| Contract governance | 4.5 |
| Operational transparency | 34.2 |
| Developer ergonomics | 71.4 |
| Access clarity | 34.2 |

**Agent readiness 43.7** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | verified |
| Auth Clarity | bearer (partial credit) |
| Idempotency | na |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | verified |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 24.5** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/bargo-congress-trades-api/](https://apis.io/providers/bargo-congress-trades-api/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Bargo Congress Trades API: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/bargo-congress-trades-api/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
