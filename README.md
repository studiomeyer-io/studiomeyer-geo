<!-- studiomeyer-mcp-stack-banner:start -->
> **Part of the [StudioMeyer MCP Stack](https://studiomeyer.io)** — Built in Mallorca 🌴 · ⭐ if you use it
<!-- studiomeyer-mcp-stack-banner:end -->

# StudioMeyer GEO

> AI visibility monitoring across 8 LLM platforms. 24 MCP tools + 5 expert workflows. Free tier: 20 tools without API keys.

[![MCP Registry](https://img.shields.io/badge/MCP-Registry-blue)](https://registry.modelcontextprotocol.io/servers/io.studiomeyer/geo)
[![MCPize](https://img.shields.io/badge/MCPize-Marketplace-purple)](https://mcpize.com/mcp/studiomeyer-geo)
[![Glama](https://glama.ai/mcp/servers/studiomeyer-io/studiomeyer-geo/badges/score.svg)](https://glama.ai/mcp/servers/studiomeyer-io/studiomeyer-geo)

## What is this?

StudioMeyer GEO checks how visible your brand is to AI assistants — across **ChatGPT, Gemini, Perplexity, Claude, Grok, DeepSeek, Meta AI, and Copilot**. Instead of guessing, you get concrete scores, citations, and actionable fixes.

**24 expert tools** for AI visibility checks, discovery stack audits, robots.txt analysis, JSON-LD validation, entity consistency, sitemap-first content freshness, page-type-aware content audits (KDD 2024 GEO paper), retrieval quality (text-to-HTML ratio + JS dependency + canonical chains), GEO score simulation, citation source analysis, schema generation, hallucination guard for LLM-derived facts, competitor comparison, and historical trend tracking.

**20 of 24 tools work without any LLM API key** — zero-cost onboarding.

## Connect in 10 Seconds

### Claude Desktop / Cowork
Settings → Connectors → Add URL:
```
https://geo.studiomeyer.io/mcp
```
You'll receive a sign-in link via email to verify your identity — no passwords needed.

### Claude Code
```bash
claude mcp add --transport http geo https://geo.studiomeyer.io/mcp
```

### Cursor / VS Code / Windsurf / Zed
```bash
npx mcp-remote https://geo.studiomeyer.io/mcp
```

## Tools (24)

### Base Tools (7)
| Tool | Description | API Key |
|------|-------------|:---:|
| `geo_check` | Full GEO check pipeline across 8 LLM platforms | Yes (1+) |
| `geo_discovery_stack` | llms.txt + agents.json + robots.txt + JSON-LD + sitemap + FAQ schema | No |
| `geo_calculate_score` | Pure scoring function from raw data | No |
| `geo_platforms` | LLM platform readiness check (8 platforms) | No |
| `geo_preview_prompts` | Preview prompts without making API calls | No |
| `geo_analyze_response` | Parse a single LLM response for brand mentions. Optional hallucination guard (`verifyUrls`, `extractClaims`, `claimsReference`) cross-checks LLM-cited URLs against the real web and tags numeric claims as verified / refuted / unverified. | No |
| `geo_recommendations` | Generate actionable recommendations from scores | No |

### Specialist Tools (10)
| Tool | Description | API Key |
|------|-------------|:---:|
| `geo_robots_audit` | Deep robots.txt analysis with 14-AI-bot matrix | No |
| `geo_llms_txt_validate` | Validate llms.txt against llmstxt.org spec with link checking | No |
| `geo_json_ld_audit` | Extract and audit JSON-LD structured data | No |
| `geo_entity_consistency` | Scan for brand name variants. Masks emails, URLs, and bare brand-domain refs before matching, so `ahoi@example.com` is not counted as a variant. Fragmented entities = 2.8x fewer AI citations. | No |
| `geo_content_freshness` | Sitemap-first freshness audit. Reads robots.txt, walks sitemap_index, scores top-N URLs by lastmod + Last-Modified + og:modified_time + schema dateModified. Hardcoded i18n paths only as last-resort fallback. | No |
| `geo_simulate` | Estimate GEO score without API keys (~30s, free) | No |
| `geo_schema_generator` | Generate missing JSON-LD blocks ready to paste | No |
| `geo_citation_sources` | Citability score: authority links, stats, sameAs, quotes | No |
| `geo_content_audit` | Page-type-aware deep content audit. Detects homepage / blog post / product / local business / about / profile / service / category / contact via JSON-LD `@type` (with URL-pattern fallback) and applies a tailored weighting profile per type. Based on KDD 2024 GEO paper. | No |
| `geo_retrieval_quality` | Static crawler-readiness audit (no headless browser). Text-to-HTML ratio, visible-text length, JS-required markers (DE+EN), `<noscript>` fallback, meta refresh, canonical mismatch, redirect chain depth via HEAD probe. Score 0..100 + issues. | No |

### Comparison + Agency Tools (3)
| Tool | Description | Tier |
|------|-------------|:---:|
| `geo_compare` | Side-by-side GEO comparison of two brands | Free |
| `geo_brands` | Multi-brand management (list/add/remove/dashboard) | Team |
| `geo_bulk_check` | Bulk GEO check across all tracked brands | Team |

### Pro Tools (4)
| Tool | Description | Tier |
|------|-------------|:---:|
| `geo_history` | Past check results with score progression | Pro |
| `geo_trends` | Score trends: delta, direction, min/max/avg | Pro |
| `geo_schedule` | Automated checks (daily/weekly/monthly) | Pro |
| `geo_alerts` | Score-drop / new issues / resolved alerts | Pro |

## MCP Prompts (5 Expert Workflows)

| Prompt | Use Case |
|--------|----------|
| `/geo_full_audit` | Complete chain of all specialists + executive report |
| `/geo_quick_wins` | API-free checks only, ~30 seconds, quick wins |
| `/geo_before_launch` | 8-point launch checklist with BLOCK/PASS gates |
| `/geo_competitor_intel` | Discover which brands AI recommends instead of yours |
| `/geo_track_over_time` | Run check + store results + compare with previous runs |

## GEO Score (0-100)

Six weighted sub-scores:
- **Brand Awareness** (25%) — How often LLMs mention your brand
- **Citation Strength** (20%) — URL citations and source links
- **Share of Voice** (20%) — Your brand vs competitors
- **Sentiment** (10%) — Positive/negative/neutral perception
- **Discovery Stack** (15%) — Technical AI-readiness (llms.txt, agents.json, JSON-LD, etc.)
- **Content Quality** (10%) — Freshness, structured data, FAQ schema

Rating: 80+ excellent · 65+ good · 40+ needs improvement · 20+ weak · <20 critical

## What Makes This Different

| Feature | Ahrefs Brand Radar | Profound | Peec AI | Otterly | **StudioMeyer GEO** |
|---------|:---:|:---:|:---:|:---:|:---:|
| Free tier | — | — | — | — | **20 tools** |
| LLM platforms | 6 | 10+ | 4 | 6 | **8** |
| MCP native | — | — | — | — | **Yes** |
| Discovery Stack depth | — | — | — | — | **Yes** |
| Fix guidance + schema gen | — | — | Partial | Partial | **Yes** |
| Content audit (KDD 2024) | — | — | — | — | **Yes** |
| Citation source analysis | — | — | — | — | **Yes** |
| Starting price | ~$700/mo | $399/mo | $89/mo | $29/mo | **Free** |

## Pricing

| Plan | Price | Includes |
|------|-------|---------|
| **Free** | €0 | 24 tools, 8 platforms, hosted MCP, OAuth 2.1 |
| **Pro** | €49/mo | History, trends, scheduled checks, alerts, PDF reports |
| **Team** | €99/mo | Multi-brand dashboard, agency features, bulk checks |
| **Managed Monitoring** | €499/mo | Monthly executive report + quarterly strategy call |
| **Full GEO Service** | €999 + €299/mo | Done-for-you consulting + implementation |

## Security

- **Magic Link Authentication** — email verification on every sign-in. No passwords stored. You receive a single-use link that expires in 10 minutes. Nobody can access your data without proving email ownership.
- **OAuth 2.1** with PKCE S256 — latest authentication standard
- **Cloudflare Proxy** — DDoS protection, WAF, SSL termination
- **Rate Limiting** — per-token (30 req/min) and per-endpoint
- **SSRF Protection** — IP encoding bypass prevention, per-hop redirect validation
- **Docker Hardened** — non-root user, read-only filesystem, cap_drop ALL

## Example: Quick Audit

```
You: /geo_quick_wins url=https://example.com

Claude runs 10 API-free specialist checks:
  ✓ robots.txt AI-bot audit (14 bots)
  ✓ llms.txt validation
  ✓ JSON-LD structured data audit
  ✓ Entity consistency scan (with email/URL/domain mask)
  ✓ Content freshness (sitemap-first)
  ✓ Page-type-aware content audit
  ✓ Retrieval quality (text-to-HTML, JS dependency, canonical chain)
  ✓ Citation source analysis
  ✓ GEO score simulation
  ✓ Schema generator (missing blocks)

Result: Estimated score, issues found, prioritized fix list with copy-paste JSON-LD
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

## What's New

**2026-04-13 — v2.0.4 (Benny Windolph Feedback Wave)**

Six fixes shipped after detailed feedback from a DACH SEO professional:

1. **Page-type-aware content audit** — `detectPageType()` (JSON-LD `@type` first, URL-pattern fallback) plus per-type weighting profile. A homepage isn't judged on expert quotes or author attribution any more.
2. **Sitemap-first content freshness** — reads robots.txt, walks sitemap_index recursively, scores real URLs by lastmod. Hardcoded i18n paths only as last-resort fallback.
3. **Entity consistency mask** — emails, absolute URLs, and bare brand-domain references are masked before matching. Fixes the `ahoi@example.com` false-positive.
4. **New `geo_retrieval_quality` specialist** — static crawler-readiness audit (no headless browser).
5. **Hallucination guard helpers** — wired into `geo_analyze_response` as opt-in parameters.
6. **Default LLM models bumped off the smallest tier** — `gpt-5-mini` (chatgpt), `claude-sonnet-4-5` (claude), `gemini-2.5-flash` (gemini). The smallest tiers had weaker entity recall and one was silently rejecting calls.

## About StudioMeyer

[StudioMeyer](https://studiomeyer.io) is an AI and design studio from Palma de Mallorca, building custom websites and AI infrastructure for small and medium businesses. Production stack on Claude Agent SDK, MCP, n8n and an in-house observability and guard layer.

## License

MIT — see [LICENSE](LICENSE). This repository contains documentation only.
The GEO server is hosted at [geo.studiomeyer.io](https://geo.studiomeyer.io).