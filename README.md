# Present of AI MCP server

Free, read-only, no-auth remote MCP server over presentofai.com data: about 4,900 AI companies (around 4,000 with a sourced Spotlight), open AI jobs and dated AI news. Every result carries its canonical presentofai.com URL and an attribution line (CC BY 4.0). Please link back to the page you use.

- Endpoint: `https://presentofai.com/mcp` (Streamable HTTP, JSON-RPC 2.0 over POST, stateless)
- Server card: `https://presentofai.com/.well-known/mcp/server-card.json`
- REST twin: `https://presentofai.com/api/v1` (OpenAPI at `/api/v1/openapi.json`)
- Docs: https://presentofai.com/developers
- Rate limit: 60 requests per minute per IP

## Tools

| Tool | Purpose |
| --- | --- |
| `search_ai_companies` | Find companies by topic, sector, country, stage, founded year, hiring |
| `get_company` | One company in detail by slug |
| `list_sectors_countries` | Valid filter values with counts |
| `find_ai_jobs` | Open roles by keyword, company, function, place |
| `latest_ai_news` | Dated, source-linked AI news |
| `whats_trending` | Trending topics and top hiring companies |

## Connect

```
claude mcp add --transport http present-of-ai https://presentofai.com/mcp
```

```json
{ "mcpServers": { "present-of-ai": { "type": "http", "url": "https://presentofai.com/mcp" } } }
```

Protocol versions served: 2024-11-05, 2025-03-26, 2025-06-18, 2025-11-25 (initialize handshake) and 2026-07-28 (per-request metadata, no initialize needed). No sessions, no GET stream (GET returns 405).

## Registry listing files (nothing has been submitted)

- `smithery.yaml`: optional, see comments inside.
- Steps for each directory are in `growth/mcp-api.md`.
