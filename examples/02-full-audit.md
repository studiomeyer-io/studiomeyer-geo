# Full GEO Audit — With LLM API Keys

Run a complete AI visibility check across ChatGPT, Gemini, Perplexity, and Claude.

## Prerequisites

Set one or more API keys as environment variables:
- `OPENAI_API_KEY` — for ChatGPT checks
- `GOOGLE_AI_API_KEY` — for Gemini checks
- `PERPLEXITY_API_KEY` — for Perplexity checks
- `ANTHROPIC_API_KEY` — for Claude checks

More platforms = more accurate GEO score.

## Using MCP Prompt

```
/geo_full_audit url=https://your-website.com brand=YourBrand
```

Claude runs the complete pipeline:
1. All 6 API-free specialist checks
2. Brand mention checks across configured LLM platforms
3. Citation and URL tracking
4. Sentiment analysis
5. GEO score calculation (0-100)
6. Prioritized recommendations

## GEO Score Breakdown

| Sub-Score | Weight | What it Measures |
|-----------|--------|-----------------|
| Brand Awareness | 25% | Do LLMs know your brand? |
| Citation Strength | 20% | Do they link to your site? |
| Share of Voice | 15% | How often mentioned vs competitors? |
| Sentiment | 15% | Positive, neutral, or negative? |
| Discovery Stack | 15% | Technical AI-readiness signals |
| Content Quality | 10% | Freshness, structure, entity consistency |

## Track Over Time

Use `/geo_track_over_time` with [StudioMeyer Memory](https://github.com/studiomeyer-io/studiomeyer-memory) to store results and see monthly trends.
