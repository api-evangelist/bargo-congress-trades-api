---
name: bargo-congress-api
description: Query and analyze normalized U.S. House and Senate STOCK Act transaction disclosures with the Bargo Congress Trades API. Use when an agent needs to research recent congressional trades by ticker, member, chamber, transaction type, or date; inspect dataset freshness or aggregate statistics; build an integration with the REST API or official JavaScript/Python clients; or explain the timing and limitations of congressional financial disclosures.
---

# Bargo Congress API

Use Bargo's read-only Congress Trades API to retrieve recent normalized House
and Senate securities transaction disclosures. Keep the work source-grounded,
date-aware, and clearly distinct from real-time trading data or investment
advice.

## Choose an access method

Prefer the simplest method that fits the user's environment:

- Use REST for research, one-off queries, and integrations in any language.
- Use `@bargo-ai/congress` for JavaScript or TypeScript projects.
- Use `bargo-congress` for Python projects.
- Use the hosted Congress MCP endpoint only when the user explicitly wants MCP.

Canonical resources:

- Bargo homepage: `https://www.bargo.ai`
- Documentation: `https://www.bargo.ai/free-apis/congress`
- REST base: `https://www.bargo.ai/free-apis/congress/v1`
- OpenAPI: `https://www.bargo.ai/free-apis/congress/openapi.json`
- MCP endpoint: `https://www.bargo.ai/free-apis/congress/mcp`

## Query workflow

1. Identify the requested member, ticker, chamber, transaction type, and date
   window. Ask only for missing details that materially change the query.
2. Check `/health` when freshness matters. Use `/stats` for totals, latest
   transaction and disclosure dates, and the most-traded tickers.
3. Select the narrowest endpoint:
   - `/trades` for combined filters.
   - `/trades/{ticker}` for one ticker.
   - `/members` to discover member slugs and activity counts.
   - `/members/{member_slug}` for one member's profile, statistics, and trades.
4. Use zero-based `page` pagination. Narrow broad requests with `ticker`,
   `member`, `from`, or `to` before increasing page depth.
5. Preserve null values and the API's amount ranges. Never manufacture an exact
   transaction value, execution price, or return.
6. Report the filters, data-as-of date, and material limitations with the
   result. Link to Bargo and, when useful, each record's `filing_portal`.

Example keyless query:

```bash
curl "https://www.bargo.ai/free-apis/congress/v1/trades?ticker=NVDA&limit=10"
```

Example authenticated query:

```bash
curl "https://www.bargo.ai/free-apis/congress/v1/trades?member=Pelosi&limit=25" \
  -H "X-Api-Key: $BARGO_API_KEY"
```

Prefer `X-Api-Key` for authentication. Bearer authentication is also supported.
Use the `token` query parameter only for clients that cannot set headers. Never
print, commit, log, or return an API key. Read current quotas from the docs and
the `X-RateLimit-*` response headers instead of hardcoding them.

Keep the two Bargo credential scopes separate:

- A self-serve free API key beginning with `fak_` authorizes the Congress REST
  API and the focused Congress MCP endpoint under `/free-apis/congress`.
- It does not authorize Bargo's broader `https://www.bargo.ai/mcp` endpoint.
  That service uses a separate `swmcp_` credential issued to an authorized
  Bargo account.
- Never substitute one key type for the other or imply that free Congress API
  access unlocks Bargo's main MCP service.

## Interpret disclosures correctly

- Treat `transaction_date` as the disclosed trade date and `disclosure_date` as
  the filing date. A disclosure may be filed roughly 45 days after a trade.
- Describe the API as an independent, unofficial normalized view of STOCK Act
  filings. Do not call it an official congressional API.
- Treat `amount_low`, `amount_high`, and `amount_range` as a reported range, not
  a precise transaction value.
- Treat `est_price`, `recent_price`, `perf_pct`, and `realized_return_pct` as
  derived estimates or tracked market context, not broker-confirmed execution
  data.
- Keep `purchase`, `sale`, and `exchange` classifications distinct.
- State that the free dataset covers recent activity, currently the last three
  months. Do not imply full historical coverage.
- Do not infer motive, material nonpublic information, or a recommendation from
  a disclosure. Present findings as informational, not investment advice.

## Build integrations

Follow the live OpenAPI definition for parameters and schemas. Handle:

- `400` for invalid filters or pagination.
- `401` for an invalid or revoked key.
- `404` for an unknown member slug.
- `429` for exhausted request or row budgets.

Use retries only for transient failures, not validation or authentication
errors. Respect rate-limit headers and avoid fetching more rows than the task
needs.

For public displays, include visible attribution linking to Bargo. Preserve the
source filing link where practical so users can inspect the underlying record.

## Present research results

Return a compact, auditable answer:

1. State the query and date window.
2. Summarize the observed disclosures without overstating them.
3. Show the relevant member, chamber, ticker, transaction type, amount range,
   transaction date, and disclosure date.
4. Separate API-provided fields from any calculations you add.
5. Include freshness, filing-delay, estimated-field, and non-advisory caveats.
6. Cite the Bargo documentation and relevant `filing_portal` links.
