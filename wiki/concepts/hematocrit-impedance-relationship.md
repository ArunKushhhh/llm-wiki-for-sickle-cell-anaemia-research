---
title: "Hematocrit–Impedance Relationship"
type: concept
tags: [hematocrit, impedance, rbc, whole-blood, low-frequency, anemia, dielectric, cell-suspension]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["electrical-impedance-spectroscopy"], ["rbc-electrical-model"], ["anemia"], ["point-of-care-diagnostics"], ["screen-printed-carbon-electrodes"]]
---

# Hematocrit–Impedance Relationship

## Core Principle

At **low frequencies (up to ~100 kHz)**, the electrical impedance of whole blood is directly proportional to hematocrit (HCT) — the fraction of blood volume occupied by red blood cells (RBCs).

**Physical basis:**
- RBC membranes act as capacitors; at low frequencies, the membrane is effectively **insulating**
- Current is forced to flow exclusively through the **extracellular medium** (plasma), around the cells
- More RBCs = smaller extracellular volume = **longer, more tortuous current path = higher impedance**
- Therefore: **ZCELL ∝ HCT** at low frequencies

This is a **purely physical, reagent-free, label-free measurement** — no chemistry, no DNA, no optical components required.

## Frequency Dependence

| Frequency Range | Signal Path | Sensitivity to HCT |
|----------------|-------------|-------------------|
| Low (< 100 kHz) | Extracellular only (around RBCs) | **High** — ideal for HCT |
| High (> 1 MHz) | Through cell membranes + intracellular | Low — HCT-insensitive |
| ~33 kHz (optimal) | Extracellular dominant | **Validated for HCT detection** |

> [!IMPORTANT] Validated operating frequency
> Hill and Thompson (1975) confirmed the hematocrit–impedance relationship at ≤100 kHz. The Punter-Villagrasa device ([[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis]]) specifically uses **33 kHz** as the operating frequency, chosen empirically for the Dropsens C223AT sensor. This contrasts sharply with the DNA-based EIS in [[sources/thamwarokun-2023-eis-alpha-thal-spce]] which operates at **0.58 Hz**.

## Contrast with DNA-Based EIS

The hematocrit–impedance relationship is a **bulk, whole-blood property**, whereas the DNA biosensor (H33258 + SPCEs) detects **surface blocking at the electrode**. These are completely different physical phenomena operating at very different timescales:

| Property | HCT-EIS (this concept) | DNA EIS (Thamwarokun) |
|----------|----------------------|----------------------|
| Frequency | 33 kHz | 0.58 Hz |
| Signal origin | Bulk RBC volume fraction | Surface blocking by H33258–dsDNA |
| Sample | Whole blood (50 µL) | mPCR amplicons in buffer |
| Target analyte | Red blood cell count/size | DNA sequence presence |
| Specificity | HCT (all-cause anemia) | SEA deletion genotype |
| Preprocessing | None | DNA extraction + mPCR |

## RBC Morphology as a Potential Discriminator

> [!QUESTION] Key open question for research focus
> Normal RBCs are biconcave discs (~8 µm diameter, ~2 µm thick). Sickle RBCs (HbS) polymerize under deoxygenation and adopt crescent/elongated shapes. **Would HbS cells produce a different impedance signature than normal cells at the same HCT?**
> 
> Potential discriminating factors:
> - Different cell morphology → different surface-area-to-volume ratio → different extracellular tortuosity
> - HbS polymerization may alter membrane rigidity and capacitance (RM, CM in the RC model)
> - Abnormal sickling may alter the intracellular resistance (RI) due to hemoglobin aggregation
> 
> If the answer is yes, a frequency sweep (rather than a single frequency) over whole blood might discriminate HbS from HbA without any molecular assay. This is a high-value unexplored direction.

## Validated Performance (from [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis]])

- **Range validated:** HCT 14.2% – 50.6% (full clinically relevant anemia spectrum)
- **Correlation:** Pearson r = −0.96 (inverse: higher HCT → lower output voltage)
- **Accuracy:** 2.83% HCT error; CV = 2.57% (all < 5% per clinical QC)
- **Response time:** Milliseconds (instantaneous)
- **Sample volume:** 50 µL (capillary-compatible)

## Sources Informing This Page

- [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis|Punter-Villagrasa et al. (2015)]] — primary source; device design, validation, and full mechanism explanation
