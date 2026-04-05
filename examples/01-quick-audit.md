# Quick Audit — No API Keys Needed

Run 6 expert checks in ~30 seconds without any LLM API key.

## Using MCP Prompt

```
/geo_quick_wins url=https://your-website.com
```

Claude will run these checks automatically:
1. **robots.txt AI-bot audit** — Are you blocking ChatGPT, Google-Extended, Anthropic, etc.?
2. **llms.txt validation** — Does your llms.txt follow the spec? Are linked URLs reachable?
3. **JSON-LD audit** — Is your structured data complete? Missing sameAs, dateModified?
4. **Entity consistency** — Is your brand name consistent? ("StudioMeyer" vs "Studio Meyer" vs "studiomeyer.io")
5. **Content freshness** — When was your content last updated? Stale content gets fewer citations.
6. **Discovery stack** — Do you have llms.txt, agents.json, robots.txt AI rules, FAQ schema?

## Using Individual Tools

```
geo_robots_audit url=https://your-website.com
```

Returns a 14-bot allow/block matrix:

| Bot | Status | Owner |
|-----|--------|-------|
| GPTBot | Allowed | OpenAI |
| Google-Extended | Blocked | Google |
| ClaudeBot | Allowed | Anthropic |
| ... | ... | ... |

Plus detection of common mistakes like blocking `/_next/` (breaks Next.js indexing).

## What to Do with Results

- **Score > 70:** You're ahead of most competitors. Focus on content quality.
- **Score 40-70:** Quick wins available. Fix robots.txt and add llms.txt first.
- **Score < 40:** Significant gaps. Consider the [GEO Service](https://studiomeyer.io/en/services/geo-mcp) for guided optimization.
