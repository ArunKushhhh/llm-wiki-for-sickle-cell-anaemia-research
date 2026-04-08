---
title: "Label-Free EIS Biosensor for α-Thalassemia 1 (SEA Deletion) Detection via SPCEs"
type: source
tags: [eis, alpha-thalassemia, screen-printed-electrodes, biosensor, point-of-care, mPCR, hoechst-33258, dna-detection]
created: 2026-04-09
updated: 2026-04-09
related: [["electrical-impedance-spectroscopy"], ["alpha-thalassemia"], ["screen-printed-carbon-electrodes"], ["hoechst-33258"], ["point-of-care-diagnostics"], ["multiplex-pcr"]]
---

# Label-Free EIS Biosensor for α-Thalassemia 1 (SEA Deletion) Detection via SPCEs

## Citation

**Title:** A label-free electrochemical biosensor for the detection of alpha-thalassemia 1 (SEA deletion) carriers using screen-printed carbon electrodes  
**Authors:** Areenuch Thamwarokun, Chollanot Kaset, Chanpen Karuwan, Wichayaporn Kamsong, Jirapat Attapong, Sirinart Chomean (corresponding)  
**Institution:** Thammasat University, Faculty of Allied Health Sciences; National Science and Technology Development Agency (NSTDA), Thailand  
**Status:** Preprint (not peer-reviewed) — SSRN:4459113  
**Year:** ~2023  
**Funding:** Thailand Graduate Institute of Science and Technology (TGIST), NSTDA (Grant No. SCA-CO-2561-7120TH)

Raw source: `[[raw/A label-free electrochemical biosensor for the detection of alpha-thalassemia 1 (SEA deletion) carriers using screen-printed carbon electrodes.pdf]]`

---

## Abstract / TL;DR

This paper develops a label-free electrochemical DNA biosensor using screen-printed carbon electrodes (SPCEs) and Hoechst 33258 (H33258) dye to detect carriers of α-thalassemia 1 (SEA deletion) — the most common inherited blood disorder in Southeast Asia. The sensor couples multiplex PCR (mPCR) amplification with EIS measurement and achieves 100% sensitivity, 88.2% specificity, and 92.6% accuracy on 81 clinical blood samples. It costs ~$2 per test, reduces turnaround time 45-fold compared to gel electrophoresis, and establishes concrete EIS parameters (0.58 Hz, 300 mV constant potential) for a future integrated mini-potentiostat.

---

## Key Contributions

- First reported label-free EIS biosensor specifically designed to detect α-thalassemia 1 (SEA deletion) — a large 20.5 kb deletion — in clinical samples (not just synthetic DNA)
- Identifies optimal EIS frequency: **0.58 Hz** for maximal discrimination between normal and SEA-deleted α-globin genes
- Demonstrates Rct (charge transfer resistance) as more reliable than -Z″ (negative imaginary impedance) for clinical samples due to lower false-positive rate
- Shows EIS is **2× more sensitive** than conventional gel electrophoresis at low DNA concentrations (12.5 ng detection threshold)
- Sets concrete impedance cut-offs: **>26.84 kΩ (-Z″)** and **>48.83 kΩ (Rct)** for carrier identification
- Establishes mini-potentiostat parameters: **0.58 Hz, 300 mV DC bias, 10 mV AC amplitude**
- Cost: **~$2 USD per test** vs ~$40 for conventional PCR/real-time PCR (20× cheaper)

---

## Key Claims and Evidence

| Claim | Evidence |
|-------|----------|
| EIS can discriminate SEA-deletion carriers from normal individuals | 100% sensitivity/specificity on 20 known samples; ROC AUC = 1.0 |
| Rct is more reliable than -Z″ for clinical samples | Rct specificity 88.2% vs -Z″ specificity 82.4% on 81 clinical samples; fewer false positives (6 vs 9) |
| Optimal frequency is 0.58 Hz | Bode plot analysis across 0.16–7.04 Hz; statistically significant discrimination only at 0.58 Hz |
| EIS is 2× more sensitive than gel electrophoresis | 12.5 ng DNA: EIS detects carrier; gel shows no normal band at same concentration |
| Shorter PCR amplicons give higher EIS signal | Primer set 1 (242 bp) outperformed sets with 435 bp and 700 bp amplicons |
| H33258 binds dsDNA in AT-rich minor grooves, increasing impedance | Mechanistic basis for signal: H33258–dsDNA binding reduces current, increases Rct |

---

## Methodology

**Study design:** Diagnostic accuracy study

**Step 1 — SPCE fabrication:**  
- Substrate: PET (polyethylene terephthalate)
- Working electrode (WE): carbon paste, 12.57 mm² active area
- Counter electrode (CE): carbon paste, 15.70 mm²
- Reference electrode (RE): Ag/AgCl (60:40 ratio)
- Cleaning: CV in 0.1M PBS (pH 7.4), 0–1.0V, 6 cycles, 100 mV/s
- Instrument: PalmSens4 potentiostat + PSTrace 5 software

**Step 2 — mPCR amplification:**  
- 4 primer sets designed via Primer3 (sequence acc. AY207443)
- GC content: 35–70% (39.13–68.42%)
- 35 cycles: 95°C/30s, 63°C/30s, 72°C/30s in 20 µL volume
- Verified by 1.5% agarose gel electrophoresis + UV
- Primer set 1 (shortest amplicon, ~242 bp) selected as optimal

**Step 3 — EIS measurement:**  
- Frequency sweep: 0.1 Hz – 10 kHz for characterization; 0.58 Hz for clinical testing
- Impedance metrics: Nyquist plots (–Z″ vs Z′), Rct from equivalent circuit fitting
- Redox probe: Hoechst 33258 (H33258) — binds dsDNA, quenches oxidation

**Step 4 — Clinical validation:**  
- Phase 1: 20 known samples (normal + confirmed SEA carriers) → ROC-derived cut-offs
- Phase 2: 81 blood samples with MCV < 80 fL from Thammasat University Hospital
- Ground truth: conventional PCR as reference method
- Statistical tools: MedCalc v18.2.1, Spearman correlation, Bland-Altman analysis, paired t-test

---

## Results Summary

**Cut-off values** (from 20 known samples at 0.58 Hz):
- -Z″ > **26.84 kΩ** → carrier
- Rct > **48.83 kΩ** → carrier

**Mean impedance values (known samples):**

| Group | Mean -Z″ | Mean Rct |
|-------|----------|----------|
| NTC (no DNA) | 25.30 ± 0.54 kΩ | 45.28 ± 1.64 kΩ |
| Normal | 25.97 ± 0.87 kΩ | 46.63 ± 1.08 kΩ |
| SEA deletion carrier | 29.98 ± 1.21 kΩ | 52.32 ± 1.81 kΩ |

**Clinical performance on 81 samples (Rct, the better metric):**

| Metric | Value |
|--------|-------|
| Sensitivity | 100% (88.4–100.0) |
| Specificity | 88.2% (76.1–95.6) |
| PPV | 83.3% |
| NPV | 100% |
| Accuracy | 92.6% |

**Correlation:** Pearson's r = 0.884 (p<0.0001) between -Z″ and Rct; Bland-Altman mean difference = 55.8 kΩ (limit of agreement: 54.9–56.6 kΩ, 1 outlier).

---

## Limitations and Open Questions

> [!WARNING] Not peer-reviewed  
> This is a preprint. The clinical performance figures (especially specificity) should be treated as preliminary until peer review.

- **Specificity not perfect (88.2%):** 6 false positives on clinical samples. Authors attribute this to inhibitors in blood samples affecting mPCR purity. The H33258 binding is non-specific to sequence — it binds any dsDNA — so purity of mPCR product is critical for specificity.
- **NTC vs normal indistinguishable:** EIS cannot differentiate a failed (no-template) reaction from a true normal result. Requires careful sample handling.
- **PCR step is a bottleneck:** mPCR takes ~1.5 hrs and requires thermocycler. Not suitable for fully resource-constrained POC without further development.
- **Only SEA deletion tested:** Does not address other α-thalassemia mutations (e.g., α-SEA heterozygous combinations) or β-thalassemia.
- **Electrode fabrication in lab:** SPCEs were custom-fabricated; commercial SPCEs may behave differently.
- **Future work needed:** Authors suggest LAMP or RPA as isothermal alternatives to mPCR for true field deployment.

---

## Connections to Research Focus

This paper is **directly central** to the research focus. It:

- Provides a concrete, validated EIS biosensor design for a hemoglobinopathy
- Gives exact EIS parameters (frequency, potential, amplicon size effects) that are actionable for replication or adaptation
- Demonstrates the mPCR+EIS pipeline applicable to resource-constrained settings ($2/test, 1-minute measurement)
- Highlights the key open problem: **specificity limited by non-specific H33258 binding** → probe-based hybridization could address this at higher cost
- Connects to [[concepts/electrical-impedance-spectroscopy]], [[concepts/screen-printed-carbon-electrodes]], [[concepts/hoechst-33258]], [[concepts/alpha-thalassemia]], [[concepts/multiplex-pcr]], [[concepts/point-of-care-diagnostics]]

> [!IMPORTANT] Benchmark paper  
> This is the most directly applicable paper to the research goal. The impedance cut-offs, frequency selection rationale, and clinical validation pipeline should be treated as baseline references for any new sensor design targeting thalassemia.

---

## Related Wiki Pages

- [[concepts/electrical-impedance-spectroscopy]] — EIS principles, Nyquist plot interpretation
- [[concepts/screen-printed-carbon-electrodes]] — SPCE fabrication and properties
- [[concepts/hoechst-33258]] — redox probe mechanism
- [[concepts/alpha-thalassemia]] — disease background, SEA deletion genetics
- [[concepts/multiplex-pcr]] — mPCR amplification strategy
- [[concepts/point-of-care-diagnostics]] — POC architecture and constraints
- [[entities/sirinart-chomean]] — corresponding author, prior work on QCM-based thal detection
