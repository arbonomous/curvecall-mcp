# CurveCall

Pay-per-call market math and token intel for AI agents via x402 (USDC on Base). Built by [arbonomous](https://github.com/arbonomous).

CoinGecko tells you the price. CurveCall tells you what your buy will do: quote, slippage and rug-risk in one paid call. No API keys, no signup. Agents pay $0.001-$0.01 per call in USDC on Base via x402 v2.

## Use it

- **MCP (streamable HTTP):** `https://curvecall.onrender.com/mcp/` - 5 tools, same x402 gating
- **HTTP API:** `https://curvecall.onrender.com` - service card at `/`, OpenAPI at `/openapi.json`
- **Agent card (A2A):** `https://curvecall.onrender.com/.well-known/agent.json`
- **llms.txt:** `https://curvecall.onrender.com/llms.txt`

Call any endpoint without `PAYMENT-SIGNATURE` to get the 402 payment request (x402 v2, `PAYMENT-REQUIRED` header).

## Tools

| Tool | Endpoint | Price |
|------|----------|-------|
| `quote_buy` | `GET /v1/quote/buy?chain=&token=&amount_usd=` | $0.01 |
| `quote_sell` | `GET /v1/quote/sell?chain=&token=&amount_usd=` | $0.01 |
| `token_snapshot` | `GET /v1/token/{chain}/{address}` | $0.001 |
| `token_risk` | `GET /v1/token/{chain}/{address}/risk` | $0.005 |
| `pretrade_check` | `GET /v1/precheck/{chain}/{address}?amount_usd=` | $0.01 |

`pretrade_check` is the one nobody else sells: full trade simulation (quote, price impact, slippage) plus rug-risk in a single call.

## Listings

- Official MCP registry: `io.github.arbonomous/curvecall`
- Smithery: `arbonomous/curvecall`
- x402scan: `curvecall.onrender.com`

## Why this repo exists

CurveCall's source lives in a private repository. This public repo is the listing and discovery anchor for directories that verify a GitHub presence. The service itself is live and pay-per-call today.
