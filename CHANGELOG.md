# Changelog

## 2.12.0 — July 2026

Current version on the hosted service (geo.studiomeyer.io): **30 tools and 5 expert workflows**.

- **Async checks that survive the client timeout** — `geo_check_start` returns a `jobId` right away and `geo_check_result` polls it. Long `mode="search"` runs no longer die on the MCP client's request timeout.
- **Citation-source provenance** — `geo_citation_report` aggregates which domains the eight LLM platforms cite you from and splits them into owned versus third-party, so you can see whether you are quoted from your own site or from someone else's summary of it.
- **Competitor gap at prompt level** — `geo_competitor_gap` lists the prompts where an LLM names a rival but not you.
- **AI-crawler access-log analysis** — `geo_crawler_log` reads your access logs and reports which AI bots requested what, and which of those requests were answered with a blocking or error status. Free, no LLM API key.
- **Real N>1 sampling** — `geo_check` takes a `samples` parameter: each prompt is queried N times and the draws are collapsed into one result plus a reproducibility summary. A single LLM query is one stochastic draw, not a measurement.
- **Entity consistency with masking** — emails, URLs and bare domain references are masked before variant matching, which keeps the comparison focused and cuts false positives.
- **One tool count** — the tool and workflow numbers reported by `/health` and the landing page are read from the actual registrations instead of being maintained by hand.

Most tools still run without any LLM API key.

## 1.0.0

Initial public release.
