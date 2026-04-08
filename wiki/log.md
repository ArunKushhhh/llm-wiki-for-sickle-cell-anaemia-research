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

## [2026-04-09] ingest | Label-free EIS biosensor for α-thalassemia 1 (SEA deletion) — Thamwarokun et al.
- Source file: `raw/A label-free electrochemical biosensor for the detection of alpha-thalassemia 1 (SEA deletion) carriers using screen-printed carbon electrodes.pdf`
- Pages created: `wiki/sources/thamwarokun-2023-eis-alpha-thal-spce.md`
- Pages created (concepts): `wiki/concepts/electrical-impedance-spectroscopy.md`, `wiki/concepts/alpha-thalassemia.md`, `wiki/concepts/screen-printed-carbon-electrodes.md`, `wiki/concepts/hoechst-33258.md`, `wiki/concepts/point-of-care-diagnostics.md`, `wiki/concepts/multiplex-pcr.md`
- Pages created (entities): `wiki/entities/sirinart-chomean.md`
- Pages updated: `wiki/index.md`, `wiki/overview.md`, `wiki/log.md`
- Key insight: EIS at 0.58 Hz using SPCEs + H33258 achieves 100% sensitivity for α-thal SEA deletion at $2/test; specificity is limited (88.2%) by PCR purity, not the sensor itself

---

## [2026-04-08] setup | Wiki initialized
- Created directory structure: raw/, wiki/, wiki/entities/, wiki/concepts/, wiki/sources/, wiki/analyses/, wiki/synthesis/
- Created: AGENTS.md (schema), wiki/index.md, wiki/log.md, wiki/overview.md, wiki/README.md
- Status: Ready for first source ingest
- Next step: Austen to fill in Research Focus section of AGENTS.md, then drop first papers into raw/
