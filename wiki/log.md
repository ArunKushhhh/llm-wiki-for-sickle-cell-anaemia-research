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

## [2026-04-09] ingest | Microfluidic EIS assessment of RBC-mediated microvascular occlusion — Man et al. (2021)
- Source file: `raw/Microfluidic electrical impedance assessment of red blood.pdf`
- Pages created: `wiki/sources/man-2021-microfluidic-eis-scd-microvascular.md`
- Pages created (concepts): `wiki/concepts/sickle-cell-disease.md`, `wiki/concepts/rbc-deformability.md`, `wiki/concepts/microfluidics.md`
- Pages created (entities): `wiki/entities/umut-gurkan.md`
- Pages updated: `wiki/concepts/electrical-impedance-spectroscopy.md` (added 10 kHz regime → now 3 regimes; source_count 2→3), `wiki/index.md`, `wiki/overview.md`
- Key insight: EIS at 10 kHz through a microfluidic capillary network (REI metric) statistically discriminates HbSS sickle cell RBCs from healthy (ROI 34.65% vs 8.02%); REI correlates with clinical hemolytic biomarkers LDH and ARC. This resolves the top open question: impedance CAN functionally distinguish SCD from healthy at the cellular level.

---

## [2026-04-09] ingest | An Instantaneous Low-Cost POC Anemia Detection Device — Punter-Villagrasa et al. (2015)
- Source file: `raw/An Instantaneous Low-Cost Point-of-Care Anemia Detection Device.pdf`
- Pages created: `wiki/sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis.md`
- Pages created (concepts): `wiki/concepts/hematocrit-impedance-relationship.md`, `wiki/concepts/anemia.md`, `wiki/concepts/rbc-electrical-model.md`
- Pages updated: `wiki/concepts/electrical-impedance-spectroscopy.md` (added 33 kHz regime; source_count 1→2), `wiki/index.md`, `wiki/overview.md`
- Key insight: At 33 kHz, whole-blood impedance directly measures hematocrit via RBC extracellular current path; this establishes a second EIS regime (cell-physical, reagent-free) complementary to the DNA-surface EIS at 0.58 Hz. Together they cover genotypic and phenotypic diagnostic layers.

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
