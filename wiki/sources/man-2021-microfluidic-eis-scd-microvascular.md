---
title: "Microfluidic EIS Assessment of RBC-Mediated Microvascular Occlusion (SCD & HS)"
type: source
tags: [microfluidics, eis, rbc, sickle-cell-disease, hereditary-spherocytosis, deformability, microvascular-occlusion, roi, rei, lab-on-chip, poc]
created: 2026-04-09
updated: 2026-04-09
related: [["electrical-impedance-spectroscopy"], ["rbc-electrical-model"], ["sickle-cell-disease"], ["rbc-deformability"], ["hematocrit-impedance-relationship"], ["microfluidics"], ["point-of-care-diagnostics"]]
---

# Microfluidic EIS Assessment of RBC-Mediated Microvascular Occlusion (SCD & HS)

## Citation

**Title:** Microfluidic electrical impedance assessment of red blood cell mediated microvascular occlusion  
**Authors:** Yuncheng Man¹, Debnath Maji¹, Ran An, Sanjay P. Ahuja, Jane A. Little, Michael A. Suster, Pedram Mohseni, Umut A. Gurkan (†corresponding)  
**¹ Co-first authors**  
**Institution:** Case Western Reserve University (Mechanical/Aerospace Eng., Electrical/Computer Eng., Biomedical Eng.); University Hospitals Cleveland; UNC Chapel Hill  
**Journal:** *Lab on a Chip* (RSC)  
**Manuscript ID:** LC-ART-11-2020-001133.R2  
**Submitted:** 18-Feb-2021  
**Funding:** NSF CAREER 1552782; NHLBI R01HL133574, U01HL117659, T32HL134622; Cure Sickle Cell Initiative (OT2HL152643); AHA 17GRNT33661005  
**Patent:** Application filed by Case Western Reserve University

Raw source: `[[raw/Microfluidic electrical impedance assessment of red blood.pdf]]`

---

## Abstract / TL;DR

This paper presents a microfluidic device with embedded capillary network–inspired micropillar arrays (3–12 µm channels) and integrated gold electrodes that measures RBC-mediated microvascular occlusion via electrical impedance — without requiring microscopy imaging. Two new biomarkers are defined: **RBC Occlusion Index (ROI)** (from imaging) and **RBC Electrical Impedance Index (REI)** (from impedance alone). REI strongly correlates with ROI (PCC = 0.987 for stiffened RBCs; PCC = 0.946 for clinical SCD/HS samples). RBCs from sickle cell disease (HbSS, n=12) and hereditary spherocytosis (n=2) produce significantly higher ROI and REI than healthy RBCs. REI also stratifies SCD patients by treatment and correlates with hemolytic biomarkers (LDH, reticulocyte count).

---

## Key Contributions

- **Proof-of-concept that EIS distinguishes sickle cell disease RBCs from healthy RBCs** — the first paper in this wiki to directly address the core research gap (SCD impedance signature)
- Defines two new quantitative metrics: **ROI** (% microcapillary occlusion, imaging-dependent) and **REI** (% impedance change, imaging-free) — REI replaces expensive microscopy for POC adaptation
- Shows REI is responsive to as little as **1% stiff RBCs** in a healthy background (ultra-sensitive to rare abnormal cells)
- Demonstrates **REI as a therapeutic efficacy benchmark**: patients on exchange transfusion, hydroxyurea, or HSCT show distinctly lower ROI/REI and correlate with LDH and reticulocyte counts
- Microfluidic capillary dimensions (3–12 µm) **mimic the in vivo capillary bed** — makes this a physiologically grounded functional assay, not just an in vitro surrogate
- **Fast:** < 5 min total data acquisition and analysis per sample
- **Near-physiologic HCT (20%)** used — relevant to real blood processing

---

## Key Claims and Evidence

| Claim | Evidence |
|-------|----------|
| REI correlates with ROI in stiffened-RBC model | PCC = 0.987, p<0.0001, N=12 |
| REI detects 1% stiff RBCs in healthy background | Statistically significant difference at 1% and 2% stiff-RBC fractions (paired t-test, p<0.05) |
| SCD RBCs produce significantly higher ROI & REI than healthy | ROI: 34.65±21.99% (SCD) vs 8.02±1.71% (healthy); p=0.018, one-way ANOVA |
| HS RBCs also elevated (different pathology, same channel) | ROI: 23.46±2.55% (HS) vs 8.02% (healthy); p<0.001 |
| REI correlates with ROI in clinical samples | PCC = 0.946, p<0.0001, N=19 |
| REI stratifies SCD patients by treatment | Group 1 (HSCT/HU/exchange transfusion): significantly lower ROI & REI; lower LDH and ARCs |
| REI correlates with LDH (hemolytic biomarker) | Group 1 vs Group 2: LDH trend p=0.052; ARC p=0.037 |
| Post-HSCT patient: ROI/REI similar to healthy | ROI: 10.08% vs 8.02±1.71%; REI: 2.44% vs 4.31±1.25% |

---

## Physical Mechanism — What Signal Does REI Capture?

This paper uses a **fundamentally different EIS modality** from the previous two sources:

| Parameter | This paper (Man et al.) | Punter-Villagrasa 2015 | Thamwarokun 2023 |
|-----------|------------------------|----------------------|-----------------|
| Signal origin | RBC **mechanical occlusion** of microcapillaries → blocked conduction path → ↑ impedance | RBC **volume fraction** in suspension → longer extracellular path → ↑ impedance | H33258–dsDNA **surface blocking** → electrode fouling → ↑ Rct |
| Frequency | 10 kHz | 33 kHz | 0.58 Hz |
| Sample | Whole blood at HCT 20%, flowing through channels | Whole blood (static drop) | mPCR amplicons in buffer (static) |
| Channel dimensions | 3–12 µm (physiologic capillary scale) | Macroscopic electrode (50 µL drop) | Macroscopic SPCE surface |
| Target property | RBC **deformability / rigidity** | RBC volume fraction (**hematocrit**) | DNA **sequence** presence |
| Discriminates disease? | **YES** — SCD HbSS vs healthy (p<0.05) | No (measures all-cause anemia) | **YES** — SEA deletion carrier vs normal |

> [!IMPORTANT] Critical breakthrough for the research focus
> This paper **directly proves** that electrical impedance can discriminate sickle cell disease RBCs from healthy RBCs. The mechanism is mechanical (stiff sickle cells occlude microcapillaries → block current), but the readout is purely electrical (REI). This is the first evidence in this wiki of disease-specific impedance differentiation at the cellular level.

### Why Sickle RBCs Have Higher Impedance

1. **HbS polymerization**: Under low oxygen tension, HbS molecules polymerize into rigid fibers → cell becomes stiff and crescent-shaped
2. **Stiff cells can't deform through narrow capillaries** (3–10 µm): they occlude the channels
3. **Occluded channels block current flow**: instead of current passing freely through the electrolyte in the open channel, it is diverted or blocked
4. **Result**: impedance measured across the array increases proportionally to the number of occluded capillaries

---

## Device Design

### Microfluidic Architecture

```
Inlet → 12-µm array (pre-filter, large aggregates) 
      → 10-µm array + gold electrodes
      → 8-µm array + gold electrodes
      → 6-µm array + gold electrodes
      → 5-µm array + gold electrodes
      → 3-µm array + gold electrodes (most critical — tightest capillary)
      → Outlet (40-µm side pathway for flow regulation)
```

- **6 micropillar arrays total**, each paired with two sputtered gold electrodes
- Arrays mimic capillary dimensions observed in vivo (down to 3 µm)
- 40-µm side pathways mimic arteriovenous anastomoses to prevent upstream clogging
- Device is **single-use, disposable** (no cross-contamination)
- Fabricated at electronics design center (standard microfabrication)

### Measurement Protocol

1. Baseline impedance measured before perfusion
2. RBC sample (20% HCT) perfused for 20 min
3. PBS wash for 20 min
4. Final impedance measured
5. REI = sum of [(I₂−I₁)/I₁] × 100% across all arrays (3–10 µm)

**Frequency:** 10 kHz  
**Total time:** < 5 min for data acquisition and analysis

### Sample Parameters

- **Hematocrit during testing:** 20% (near-physiologic, standardized)
- **RBC source:** Clinical blood samples (EDTA tubes, freshly processed)
- System noise: ±0.27% impedance change (95% CI baseline); changes below this rounded to zero

---

## Clinical Results — SCD Population (n=12 HbSS)

| Subject Group | ROI (mean ± SD) | REI (mean ± SD) | Notes |
|--------------|-----------------|-----------------|-------|
| Healthy donors (n=5) | 8.02 ± 1.71% | 4.31 ± 1.25% | Baseline |
| SCD (n=12 HbSS) | 34.65 ± 21.99% | — | p=0.018 vs healthy |
| HS (n=2) | 23.46 ± 2.55% | — | p<0.001 vs healthy |
| Group 1 SCD (HSCT/HU/transfusion) | Lower ROI & REI | Lower ROI & REI | Converging toward healthy range |
| Group 2 SCD (untreated/other) | Higher ROI & REI | Higher ROI & REI | — |

**Reproducibility:** 5 devices from different batches, one healthy donor sample: ROI = 9.03±0.89%, REI = 5.42±1.29% — highly consistent.

---

## Limitations and Open Questions

> [!WARNING] Lab-based system, not yet POC
> The current device requires syringe pump perfusion, microscopy imaging (for ROI), and benchtop impedance analyzer. The authors explicitly state future work targets POC adaptation with minimally trained personnel.

- **Small clinical cohort:** 12 SCD + 2 HS + 5 healthy. Large variance in SCD group (SD ≈ 22% for ROI). Larger validation needed.
- **Imaging still required for ROI:** REI removes imaging for routine use, but the ROI–REI correlation was validated, not REI alone as a standalone diagnostic.
- **Thalassemia not tested:** Authors explicitly flag thalassemia as a future direction. The paper's SCD and HS focus leaves this wiki's thalassemia question open.
- **Oxygen tension not controlled:** Sickling is oxygen-dependent; tests done at ambient O₂ may underestimate sickling severity (HbS polymerizes more under low-O₂ conditions). Deoxygenated testing would be a stronger discriminator.
- **HCT standardized to 20%:** Real clinical blood may vary widely; normalization required in POC use.
- **Absolute REI values device-dependent:** REI is relative within a device design; comparison across devices with different channel geometries requires normalization.

> [!QUESTION] Can this principle be applied without microfluidic channels?
> The current system requires microfabrication. Could simpler bulk-blood impedance spectroscopy (similar to Punter-Villagrasa) at an optimized frequency detect the same RBC rigidity signal? Or is the micropillar confinement essential for the discrimination?

> [!QUESTION] Does deoxygenation during measurement enhance SCD discrimination?
> Polymerization of HbS requires deoxygenation. A device that deoxygenates blood during microfluidic perfusion and measures impedance would likely show much larger REI differences between HbSS and healthy. Multiple groups have used nitrogen gas or sodium metabisulfite to deoxygenate blood in microfluidic devices.

---

## Connections to Existing Wiki Pages

> [!IMPORTANT] This paper resolves the top open question from the first ingest
> The overview had asked: *"Can EIS directly interrogate red blood cells – discriminating SCD from healthy – without PCR?"* This paper answers YES, via microfluidic channel-integrated impedance. The mechanism is mechanical (deformability-driven occlusion), not molecular/genetic.

- **[[concepts/electrical-impedance-spectroscopy]]** — adds 10 kHz as a third validated EIS frequency regime; adds microfluidic channel as a new electrode geometry
- **[[concepts/rbc-electrical-model]]** — validates that stiff RBCs produce higher impedance; mechanism extends the passive RC model to flow-through channel geometry
- **[[concepts/sickle-cell-disease]]** — primary subject of clinical testing; new concept page required
- **[[concepts/rbc-deformability]]** — central concept; new page required
- **[[concepts/microfluidics]]** — new concept page required for device architecture
- **[[concepts/hematocrit-impedance-relationship]]** — this paper uses a different impedance mechanism (occlusion) vs bulk extracellular path; contrasting point
- **[[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis]]** — both measure whole-blood impedance; different frequencies, different geometries, different target properties
- **[[entities/umut-gurkan]]** — corresponding author; new entity page required
