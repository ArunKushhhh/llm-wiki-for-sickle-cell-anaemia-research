# Wiki Log

Append-only record of all operations: ingests, queries, lint passes, and setup events. Each entry begins with `## [YYYY-MM-DD]` for easy grep parsing.

```bash
# Useful commands:
grep "^## \[" wiki/log.md | tail -10         # last 10 operations
grep "^## \[.*ingest" wiki/log.md            # all ingests
grep "^## \[.*query" wiki/log.md             # all queries
grep "^## \[.*lint" wiki/log.md              # all lint passes
```

---

## [2026-04-08] setup | Wiki initialized
- Created directory structure: raw/, wiki/, wiki/entities/, wiki/concepts/, wiki/sources/, wiki/analyses/, wiki/synthesis/
- Created: AGENTS.md (schema), wiki/index.md, wiki/log.md, wiki/overview.md, wiki/README.md
- Status: Ready for first source ingest
- Next step: Austen to fill in Research Focus section of AGENTS.md, then drop first papers into raw/
