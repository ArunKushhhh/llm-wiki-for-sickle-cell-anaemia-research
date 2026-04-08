---
title: "Point-of-Care Diagnostics"
type: concept
tags: [poc, point-of-care, diagnostics, resource-constrained, portability, disposable, biosensor]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["electrical-impedance-spectroscopy"], ["screen-printed-carbon-electrodes"], ["alpha-thalassemia"]]
---

# Point-of-Care (POC) Diagnostics

## Definition

Point-of-care (POC) diagnostics are tests performed near the patient — at the clinic, a community health post, or in the field — rather than in a centralized laboratory. The goal is rapid, actionable results with minimal equipment, cost, and technical expertise.

## The ASSURED Framework (WHO)

The WHO provides a widely-cited design target for POC diagnostics:

| Letter | Criterion |
|--------|-----------|
| **A** | Affordable |
| **S** | Sensitive |
| **S** | Specific |
| **U** | User-friendly |
| **R** | Rapid and Robust |
| **E** | Equipment-free (or minimal) |
| **D** | Delivered to those who need it |

> [!NOTE] In practice
> "Equipment-free" is aspirational. Modern POC diagnostics often allow a small, handheld instrument. The real constraints are: no cold chain required, no lab training needed, cost per test must be survivable for low-income settings.

## Trade-offs in POC Biosensor Design

| Factor | Lab Standard | POC Target |
|--------|-------------|-----------|
| Sensitivity | Very high | Acceptable loss for speed |
| Specificity | Very high | Must not false-alarm in field |
| Cost/test | $10–$100+ | $1–$5 |
| Time-to-result | Hours–days | Minutes–hours |
| Instrument complexity | Benchtop, specialized | Handheld, battery-powered |
| Training required | High | Minimal (non-lab worker) |
| Throughput | High (batched) | Low (single sample) |

## The PCR Bottleneck in Molecular POC

The biggest challenge for molecular (DNA-based) POC diagnostics is that PCR requires:
- Thermal cycling (thermocycler)
- ~1.5 hrs min
- Precise temperature control
- Electricity (often reliable supply)

**Isothermal alternatives under development:**
- **LAMP** (Loop-mediated isothermal amplification): single temperature (~65°C), ~30–60 min
- **RPA** (Recombinase polymerase amplification): room temperature, ~20 min
- Both are compatible with SPCEs and EIS detection

> [!IMPORTANT] Key gap flagged in [[sources/thamwarokun-2023-eis-alpha-thal-spce]]
> The Thamwarokun EIS biosensor still requires conventional mPCR (1.5 hrs, thermocycler). Authors explicitly recommend LAMP or RPA as next step to make the system truly field-deployable. This is a significant open engineering gap.

## Mini-Potentiostat Design Parameters

From [[sources/thamwarokun-2023-eis-alpha-thal-spce]], a mini-potentiostat for α-thalassemia SEA detection should implement:
- **Measurement frequency:** 0.58 Hz (single-frequency EIS)
- **DC bias potential:** 300 mV
- **AC amplitude:** 10 mV
- This simplification (single frequency vs full sweep) dramatically reduces hardware complexity and measurement time

## Resources vs Performance in the Research Agenda

The research focus explicitly prioritizes:
- Rural and resource-constrained deployment
- Scalability and affordability over maximal theoretical performance
- Robustness (not failing in low-resource conditions)

This means any biosensor design should be evaluated against realistic field conditions, not just lab ideal conditions.

> [!QUESTION] Open question
> What is the minimum viable hardware stack for a complete α-thalassemia POC device (isothermal amplification + EIS measurement + readout)? What is the realistic BOM cost at 1000-unit production scale?

## Sources Informing This Page

- [[sources/thamwarokun-2023-eis-alpha-thal-spce|Thamwarokun et al. (~2023)]] — $2/test cost benchmark; 45× turnaround improvement; mini-potentiostat parameters; PCR bottleneck discussion
