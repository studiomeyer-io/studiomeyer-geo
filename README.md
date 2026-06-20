<!-- studiomeyer-mcp-stack-banner:start -->
> **Part of the [StudioMeyer MCP Stack](https://studiomeyer.io)** — Built in Mallorca 🌴 · ⭐ if you use it
<!-- studiomeyer-mcp-stack-banner:end -->

# StudioMeyer GEO

[![smithery badge](https://smithery.ai/badge/cod-gb2l/StudioMeyer-GEO)](https://smithery.ai/servers/cod-gb2l/StudioMeyer-GEO)

> AI visibility monitoring across 8 LLM platforms. 28 MCP tools + 5 expert workflows. Free tier: 21 tools without API keys.

[![MCP Registry](https://img.shields.io/badge/MCP-Registry-blue)](https://registry.modelcontextprotocol.io/servers/io.studiomeyer/geo)
[![MCPize](https://img.shields.io/badge/MCPize-Marketplace-purple)](https://mcpize.com/mcp/studiomeyer-geo)
[![Glama](https://glama.ai/mcp/servers/studiomeyer-io/studiomeyer-geo/badges/score.svg)](https://glama.ai/mcp/servers/studiomeyer-io/studiomeyer-geo)

## A note from us

We have been building tools and systems for ourselves for the past two years. The fact that this repo is small and has few stars is not because it is new. It is because we only just decided to share what we have built. It is not a fresh experiment, it is a long story with a recent commit.

We love building things and sharing them. We do not love social media tactics, growth hacks, or chasing stars and followers. So this repo is small. The code is real, it gets used, issues get answered. Judge for yourself.

If it helps you, sharing, testing, and feedback help us. If it could be better, an issue is more useful. If you build something with it, tell us at hello@studiomeyer.io. That genuinely makes our day.

From a small studio in Palma de Mallorca.

## What is this?

StudioMeyer GEO checks how visible your brand is to AI assistants — across **ChatGPT, Gemini, Perplexity, Claude, Grok, DeepSeek, Meta AI, and Copilot**. Instead of guessing, you get concrete scores, citations, and actionable fixes.

**28 expert tools** for AI visibility checks, discovery stack audits, robots.txt analysis, JSON-LD validation, entity consistency, sitemap-first content freshness, page-type-aware content audits (KDD 2024 GEO paper), retrieval quality (text-to-HTML ratio + JS dependency + canonical chains), GEO score simulation, citation source analysis, schema generation, hallucination guard for LLM-derived facts, citation-source provenance (which domains the 8 LLMs actually cite you from), prompt-level competitor-gap reports, AI-crawler access-log analysis (which AI bots crawl you, and whether you're blocking them), competitor comparison, and historical trend tracking.

**21 of 28 tools work without any LLM API key** — zero-cost onboarding.

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

## Tools (28)

### Base Tools (7)
| Tool | Description | API Key |
|------|-------------|:---:|
| `geo_check` | Full GEO check pipeline across 8 LLM platforms. Optional `samples` (N>1) runs each prompt N times and collapses the draws into one statistically-defensible result + a reproducibility summary (a single LLM query is one stochastic draw, not a measurement). | Yes (1+) |
| `geo_discovery_stack` | llms.txt + agents.json + robots.txt + JSON-LD + sitemap + FAQ schema | No |
| `geo_calculate_score` | Pure scoring function from raw data | No |
| `geo_platforms` | LLM platform readiness check (8 platforms) | No |
| `geo_preview_prompts` | Preview prompts without making API calls | No |
| `geo_analyze_response` | Parse a single LLM response for brand mentions. Optional hallucination guard (`verifyUrls`, `extractClaims`, `claimsReference`) cross-checks LLM-cited URLs against the real web and tags numeric claims as verified / refuted / unverified. | No |
| `geo_recommendations` | Generate actionable recommendations from scores | No |

### Specialist Tools (12)
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
| `geo_crawler_log` | **AI-crawler access-log analysis.** Paste raw nginx/apache logs — reports which AI bots (GPTBot, OAI-SearchBot, ClaudeBot, PerplexityBot, Google-Extended, Bytespider, CCBot, …) fetched which pages, and crucially flags BLOCKED AI requests (401/403/429/5xx). The upstream check: if the bots that feed AI answers can't fetch your pages, no on-page work will ever get you cited. | No |
| `geo_dashboard_view` | Interactive visibility dashboard (MCP Apps): score wheel with confidence range, 8-LLM heatmap, citation drift, conversation sankey, recommendations. Renders existing check data. | No |

### Citation + Competitor Tools (2)
| Tool | Description | API Key |
|------|-------------|:---:|
| `geo_citation_report` | **Citation-source provenance.** Aggregates the URLs the 8 LLMs actually cite about your brand into a classified breakdown (owned / Reddit / YouTube / Wikipedia / social / review sites / news / competitor / other) with an owned-vs-third-party split. ~97% of AI citations come from non-Tier-1 domains — this shows where to invest. | Yes (1+) |
| `geo_competitor_gap` | **Prompt-level competitor gap.** Finds the exact prompts where the LLMs name a competitor but not you — the conversations you're losing — plus per-competitor standings (who beats you in the most queries vs winnable head-to-heads). | Yes (1+) |

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

The score is hallucination-aware by default: claims the LLMs make about your brand are cross-checked, and a platform whose answer is a cross-platform outlier is down-weighted, so a single model's confident hallucination can't inflate your score.

Rating: 80+ excellent · 65+ good · 40+ needs improvement · 20+ weak · <20 critical

## What Makes This Different

| Feature | Ahrefs Brand Radar | Profound | Peec AI | Otterly | **StudioMeyer GEO** |
|---------|:---:|:---:|:---:|:---:|:---:|
| Free tier | — | — | — | — | **21 tools** |
| LLM platforms | 6 | 10+ | 4 | 6 | **8** |
| MCP native | — | — | — | — | **Yes** |
| Discovery Stack depth | — | — | — | — | **Yes** |
| Fix guidance + schema gen | — | — | Partial | Partial | **Yes** |
| Content audit (KDD 2024) | — | — | — | — | **Yes** |
| Citation source analysis | — | — | — | — | **Yes** |
| Citation-source provenance | Partial | Yes | — | — | **Yes** |
| Prompt-level competitor gap | — | Yes | Yes | — | **Yes** |
| AI-crawler log analysis | — | Partial | — | — | **Yes** |
| Statistical sampling (N>1) | — | Yes | — | — | **Yes** |
| Starting price | ~$700/mo | $399/mo | $89/mo | $29/mo | **Free** |

## Pricing

| Plan | Price | Includes |
|------|-------|---------|
| **Free** | €0 | 28 tools, 8 platforms, hosted MCP, OAuth 2.1 |
| **Pro** | €49/mo *(coming soon)* | History, trends, scheduled checks, alerts, PDF reports |
| **Team** | €99/mo *(coming soon)* | Multi-brand dashboard, agency features, bulk checks |
| **Managed Monitoring** | €499/mo | Monthly executive report + quarterly strategy call |
| **Full GEO Service** | €999 + €299/mo | Done-for-you consulting + implementation |

Currently the **Free** self-service tier and the two managed services (**Managed Monitoring**, **Full GEO Service**) are available. The **Pro** and **Team** self-service tiers launch shortly — sign up for Free now and you keep your data when they ship.

## Security

- **Magic Link Authentication** — email verification on every sign-in. No passwords stored. You receive a single-use link that expires in 10 minutes. Nobody can access your data without proving email ownership.
- **OAuth 2.1** with PKCE S256 — latest authentication standard
- **Email-based tenant isolation** — your data is scoped to your verified email, so you see the same brands and history on every client you connect from
- **Cloudflare Proxy** — DDoS protection, WAF, SSL termination
- **Rate Limiting** — per-token (30 req/min) and per-endpoint
- **SSRF Protection** — DNS-rebinding guard (validates the resolved IP, not just the hostname), IP-encoding bypass prevention, per-hop redirect validation
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
- Built by [StudioMeyer](https://studiomeyer.io) — AI and design studio in Mallorca, working worldwide

## What's New

**2026-06-20 — v2.7.0 (Hardening + Citation/Competitor/Crawler tools + Sampling)**

Three new tools and a hosted-server hardening pass:

1. **`geo_citation_report`** — aggregates which sources the 8 LLMs actually cite you from (owned / Reddit / YouTube / Wikipedia / social / review / news / competitor), with an owned-vs-third-party split.
2. **`geo_competitor_gap`** — the prompts where an LLM names a competitor but not you, plus per-competitor standings.
3. **`geo_crawler_log`** — paste your access logs to see which AI bots crawl you and whether any are being blocked (the upstream check before any on-page work).
4. **Real N>1 sampling** — `geo_check` gains a `samples` parameter; each prompt is queried N times and collapsed into one statistically-defensible result with a reproducibility summary.
5. **Hardening** — tenant identity is now your verified email (consistent across clients), a DNS-rebinding SSRF guard, outbound concurrency caps, and hallucination-aware scoring on by default.

**2026-04-13 — v2.0.4 (Benny Windolph Feedback Wave)**

Six fixes shipped after detailed feedback from a DACH SEO professional:

1. **Page-type-aware content audit** — `detectPageType()` (JSON-LD `@type` first, URL-pattern fallback) plus per-type weighting profile. A homepage isn't judged on expert quotes or author attribution any more.
2. **Sitemap-first content freshness** — reads robots.txt, walks sitemap_index recursively, scores real URLs by lastmod. Hardcoded i18n paths only as last-resort fallback.
3. **Entity consistency mask** — emails, absolute URLs, and bare brand-domain references are masked before matching. Fixes the `ahoi@example.com` false-positive.
4. **New `geo_retrieval_quality` specialist** — static crawler-readiness audit (no headless browser).
5. **Hallucination guard helpers** — wired into `geo_analyze_response` as opt-in parameters.
6. **Default LLM models bumped off the smallest tier** — `gpt-5-mini` (chatgpt), `claude-sonnet-4-5` (claude), `gemini-2.5-flash` (gemini). The smallest tiers had weaker entity recall and one was silently rejecting calls.

## About StudioMeyer

[StudioMeyer](https://studiomeyer.io) is an AI and design studio based in Palma de Mallorca, working with clients worldwide. We build custom websites and AI infrastructure for small and medium businesses. Production stack on Claude Agent SDK, MCP and n8n, with Sentry, Langfuse and LangGraph for observability and an in-house guard layer.

## License

MIT — see [LICENSE](LICENSE). This repository contains documentation only.
The GEO server is hosted at [geo.studiomeyer.io](https://geo.studiomeyer.io).
