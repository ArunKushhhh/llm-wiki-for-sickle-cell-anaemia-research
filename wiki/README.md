# README — How to Use This Wiki

## Quick Start

1. **Drop a source** into `raw/` (PDF, markdown, article clipped with Obsidian Web Clipper)
2. **Tell me to ingest it** — e.g. _"ingest paper.pdf"_ or _"process the new file in raw/"_
3. **Ask questions** — I'll synthesize answers from the wiki with citations
4. **Run a lint** periodically — _"lint"_ or _"health check"_ — to catch gaps and contradictions

## The Three Operations

| Command | What it does |
|---------|-------------|
| `ingest <filename>` | Process a new source: summarize, update entities/concepts, cross-reference |
| `query <question>` | Answer a question by synthesizing across wiki pages |
| `lint` | Health check: find orphan pages, contradictions, gaps, stale claims |

## Directory Structure

```
raw/          ← Drop your papers, articles, notes here. Never modified.
raw/assets/   ← Images downloaded from clipped articles (Obsidian Web Clipper)
wiki/         ← Everything managed by the LLM
  index.md    ← Master catalog (read this first when querying)
  log.md      ← Append-only operation history
  overview.md ← Running synthesis — the "what do we know" doc
  sources/    ← One page per source
  concepts/   ← Ideas, methods, techniques
  entities/   ← People, models, orgs, datasets
  analyses/   ← Comparison tables, deep dives from queries
  synthesis/  ← Cross-cutting arguments and theses
```

## Before Your First Session

Edit **AGENTS.md** → **Research Focus** section to tell me your domain and key questions. The more specific you are, the better I can prioritize what to extract and emphasize when ingesting.

## Tips

- Use **Obsidian Web Clipper** to clip articles directly to `raw/` as markdown
- In Obsidian settings, set attachment folder to `raw/assets/` and bind a hotkey to "Download attachments" — this keeps images local
- The **Graph View** in Obsidian shows the shape of your wiki — hubs vs orphans
- If an analysis from a query is useful, ask me to file it in `wiki/analyses/` so it persists
- This wiki is a git repo — you get full version history for free
