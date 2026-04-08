---
title: "RBC Electrical Model"
type: concept
tags: [rbc, red-blood-cell, electrical-model, membrane, impedance, capacitance, dielectric, cell-suspension]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["hematocrit-impedance-relationship"], ["electrical-impedance-spectroscopy"], ["anemia"]]
---

# RBC Electrical Model

## Overview

Red blood cells (RBCs) can be modelled as **passive electrical components** when suspended in an ionic medium. This model explains why whole blood has measurable, frequency-dependent impedance that correlates with RBC volume fraction (hematocrit).

## The Passive RC Network Model

An RBC in suspension is modelled as:

```
         ┌─── CM ─── RI ───┐
 RE ─────┤                 ├─── RE ───
         └─── RM ──────────┘
```

| Component | Physical meaning |
|-----------|-----------------|
| **RE** | Extracellular medium resistance (plasma + ionic solution) |
| **CM** | Cell membrane capacitance (lipid bilayer acts as dielectric) |
| **RM** | Membrane resistance (ion channels, leakage) |
| **RI** | Intracellular resistance (cytoplasm, dominated by hemoglobin solution) |

For **dilute cell suspensions**, this model extends to a population of cells, scaled by the volume fraction (hematocrit).

## Frequency Regimes

| Frequency | Dominant path | Impedance sensitivity |
|-----------|--------------|----------------------|
| Very low (< 1 kHz) | Around cells (RE only) | Very high to HCT |
| Low–medium (1–100 kHz) | Around cells (still RE) | High to HCT — **optimal range** |
| High (> 1 MHz) | Through membrane + intracellular (RI) | Low HCT sensitivity; more sensitive to intracellular content |

At **33 kHz** (used in [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis]]):
- Current flows primarily through RE (extracellular path)
- ZCELL rises with HCT because RE effective length increases with more cells packed in
- Membrane is essentially insulating at this frequency

## Implications for Hemoglobin Variant Detection

> [!QUESTION] Can the RC model discriminate sickle vs normal RBCs?
> In sickle cell disease (HbSS), RBCs undergo polymerization under deoxygenation. Sickling changes:
> - **Cell morphology** → crescent shape → different geometric packing → different RE tortuosity
> - **Membrane rigidity** → altered CM (stiffer membranes may have different dielectric properties)
> - **Intracellular viscosity** → HbS polymer → higher RI
> 
> These changes would manifest as **frequency-dependent shifts in the impedance spectrum** beyond what is explained by HCT alone. Multi-frequency EIS (or impedance spectroscopy over a full Nyquist plot) of whole blood from HbSS vs HbAA patients at the same HCT could reveal discriminating features — an unexplored but high-value direction.

## Connection to This Research

The RBC electrical model is foundational for understanding:
1. Why bulk blood EIS at 33 kHz measures HCT (Punter-Villagrasa)
2. Why surface-EIS at 0.58 Hz detects DNA (Thamwarokun) — a completely different physical regime
3. Why the two approaches cover complementary diagnostic layers (phenotype vs. genotype)
4. What features a **multi-frequency whole-blood EIS sweep** might extract that could discriminate hemoglobinopathies

## Sources Informing This Page

- [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis|Punter-Villagrasa et al. (2015)]] — RC model for RBC suspensions; 33 kHz operating frequency rationale; current path diagrams
