# StudioMeyer GEO

> AI visibility monitoring for brands. 12 MCP tools. Measure how ChatGPT, Gemini, Perplexity, and Claude see your brand.

[![MCP Registry](https://img.shields.io/badge/MCP-Registry-blue)](https://registry.modelcontextprotocol.io/servers/io.studiomeyer/geo)

## What is this?

StudioMeyer GEO checks how visible your brand is to AI assistants. Instead of guessing, you get concrete scores, citations, and actionable fixes.

**12 expert tools** for AI visibility checks, discovery stack audits, robots.txt analysis, JSON-LD validation, entity consistency, content freshness, and fix recommendations.

6 of 12 tools work **without any LLM API key** — zero-cost onboarding.

## Connect in 10 Seconds

### Claude Desktop / Cowork
Settings → Connectors → Add URL:
```
https://geo.studiomeyer.io/mcp
```

### Claude Code
```bash
claude mcp add --transport http geo https://geo.studiomeyer.io/mcp
```

### Cursor / VS Code / Windsurf / Zed
```bash
npx mcp-remote https://geo.studiomeyer.io/mcp
```

## Tools (12)

### Base Tools (7)
| Tool | Description | API Key Required |
|------|-------------|:---:|
| `geo_check` | Full GEO check pipeline across 4 LLM platforms | Yes (1+) |
| `geo_discovery_stack` | llms.txt + agents.json + robots.txt + JSON-LD + sitemap + FAQ schema | No |
| `geo_calculate_score` | Pure scoring function from raw data | No |
| `geo_platforms` | LLM platform readiness check | No |
| `geo_preview_prompts` | Preview prompts without making API calls | No |
| `geo_analyze_response` | Parse a single LLM response for brand mentions | No |
| `geo_recommendations` | Generate actionable recommendations from scores | No |

### Specialist Tools (5)
| Tool | Description | API Key Required |
|------|-------------|:---:|
| `geo_robots_audit` | Deep robots.txt analysis with 14-AI-bot matrix | No |
| `geo_llms_txt_validate` | Validate llms.txt against llmstxt.org spec with link checking | No |
| `geo_json_ld_audit` | Extract and audit JSON-LD structured data | No |
| `geo_entity_consistency` | Scan for brand name variants (fragmented entities = 2.8x fewer AI citations) | No |
| `geo_content_freshness` | Check Last-Modified, og:modified_time, schema dateModified signals | No |

## MCP Prompts (5 Expert Workflows)

| Prompt | Use Case |
|--------|----------|
| `/geo_full_audit` | Complete chain of all specialists + executive report |
| `/geo_quick_wins` | API-free checks only, ~30 seconds, quick wins |
| `/geo_before_launch` | 8-point launch checklist with BLOCK/PASS gates |
| `/geo_competitor_intel` | Discover which brands AI recommends instead of yours |
| `/geo_track_over_time` | Run check + store results + compare with previous runs |

## What Makes This Different

| Feature | Ahrefs Brand Radar | Profound | Peec AI | Otterly | **StudioMeyer GEO** |
|---------|:---:|:---:|:---:|:---:|:---:|
| Free tier | - | - | - | - | **12 tools** |
| MCP native | - | - | - | - | **Yes** |
| Discovery Stack depth | - | - | - | - | **Yes** |
| Fix guidance | - | - | Partial | Partial | **Yes** |
| robots.txt AI-bot matrix | - | - | - | - | **14 bots** |
| llms.txt validation | - | - | - | - | **Yes** |
| Entity consistency check | - | - | - | - | **Yes** |
| Starting price | ~$700/mo | $399/mo | $89/mo | $29/mo | **Free** |

## Pricing

| Plan | Price | Includes |
|------|-------|----------|
| **Free** | $0 | 10 checks/day, all 12 tools |
| **Pro** | $29/mo | Unlimited checks, history, trends, PDF reports, email alerts |
| **Managed Monitoring** | $499/mo | Monthly executive report, quarterly strategy call, competitor tracking |
| **Full GEO Service** | Custom | Setup + ongoing optimization by StudioMeyer team |

## Example: Quick Audit

```
You: /geo_quick_wins url=https://example.com

Claude runs 6 API-free checks:
  - robots.txt AI-bot audit (14 bots)
  - llms.txt validation
  - JSON-LD structured data audit
  - Entity consistency scan
  - Content freshness check
  - Discovery stack completeness

Result: Score, issues found, prioritized fix list
```

## Optional: Track Over Time with StudioMeyer Memory

Connect [StudioMeyer Memory](https://github.com/studiomeyer-io/studiomeyer-memory) to automatically store GEO checks across sessions:

```bash
claude mcp add --transport http memory https://memory.studiomeyer.io/mcp
```

Then use `/geo_track_over_time` — Claude stores results in Memory and shows trends.

## Support

- Landing page: [studiomeyer.io/services/geo-mcp](https://studiomeyer.io/en/services/geo-mcp)
- Email: hello@studiomeyer.io
- Built by [StudioMeyer](https://studiomeyer.io) — AI agency from Spain

## License

Proprietary. Free tier available. See [Terms of Service](https://studiomeyer.io/terms).
