---
title: "Electrical Impedance Spectroscopy (EIS)"
type: concept
tags: [eis, impedance, electrochemistry, biosensing, nyquist, bode, rct, charge-transfer-resistance]
created: 2026-04-09
updated: 2026-04-09
source_count: 2
related: [["screen-printed-carbon-electrodes"], ["hoechst-33258"], ["point-of-care-diagnostics"], ["alpha-thalassemia"]]
---

# Electrical Impedance Spectroscopy (EIS)

## What It Is

EIS is an electroanalytical technique that measures how a system resists the flow of alternating current (AC) across a range of frequencies. It probes the electrical properties of interfaces — in biosensing applications, typically the electrode–solution interface — without labeling or modifying the target molecule.

**Core principle:** Apply a small AC perturbation (a sinusoidal voltage, typically 5–10 mV) at a fixed DC bias across a range of frequencies. Measure the resulting current. The impedance Z = V/I is complex: it has a real part (resistance, Z′) and an imaginary part (reactance, Z″).

## Key Parameters

| Parameter | Symbol | What it captures |
|-----------|--------|-----------------|
| Charge Transfer Resistance | Rct | Barrier to electron transfer at electrode surface. Increases as dsDNA/analyte blocks the surface. |
| Negative Imaginary Impedance | -Z″ | Capacitive component; related to double-layer capacitance. |
| Solution resistance | Rs | Resistance of electrolyte. Usually subtracted. |
| Nyquist plot | -Z″ vs Z′ | Semicircle = Rct; linear region = diffusion (Warburg) |
| Bode plot | log\|Z\| or phase vs log(frequency) | Shows frequency-dependent response |

## How It Works in DNA Biosensing

In label-free EIS biosensors:
1. A redox probe (e.g., [[hoechst-33258]], ferro/ferricyanide) is present in solution
2. Target DNA (dsDNA from PCR) is added; it binds the redox probe
3. The probe–DNA complex adsorbs to or blocks the electrode surface
4. This creates a steric/electrostatic barrier → **Rct increases**
5. The increase in Rct is proportional to the amount of dsDNA present

> [!NOTE] Label-free vs labeled
> "Label-free" means the target DNA itself is not modified with a fluorescent or electroactive tag. The signal comes from how the target DNA, once bound to the probe molecule, changes electrode behavior. This is simpler and cheaper than labeled approaches.

## Frequency Selection

The choice of measurement frequency is critical:
- Too high: dominated by solution resistance, loses sensitivity to surface events
- Too low: diffusion processes dominate, noisy
- Optimal: the frequency where the impedance response is most sensitive to analyte concentration

> [!IMPORTANT] Two validated EIS operating regimes — very different frequencies, very different physics
> 
> | Regime | Frequency | Signal origin | Source |
> |--------|-----------|--------------|--------|
> | DNA surface blocking | **0.58 Hz** | H33258–dsDNA blocks electrode surface → ↑ Rct | [[sources/thamwarokun-2023-eis-alpha-thal-spce]] |
> | RBC bulk measurement | **33 kHz** | More RBCs → longer extracellular current path → ↑ ZCELL | [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis]] |
> 
> These operate at **fundamentally different physical regimes** and measure completely different things. A single-frequency EIS device must choose one. A multi-frequency sweep could potentially access both.

## EIS vs Other Electrochemical Techniques

| Technique | Advantage | Disadvantage |
|-----------|-----------|-------------|
| EIS | Non-destructive, rich information, label-free possible | Requires equivalent circuit fitting; slower |
| CV (cyclic voltammetry) | Simple, widely understood | Less selective, destroys signal |
| DPV (differential pulse voltammetry) | Very sensitive | Requires labeled target or redox-active analyte |
| Amperometry | Simple, real-time | Single-point, less mechanistic insight |

## POC Relevance

EIS is particularly attractive for point-of-care (POC) diagnostics because:
- **Portable instruments:** Modern potentiostats (e.g., PalmSens4) are handheld and battery-powered
- **Disposable electrodes:** SPCEs eliminate cross-contamination
- **Fast measurement:** Single-frequency EIS takes ~1 minute (vs 1–2 hrs for gel electrophoresis)
- **No optical components:** Unlike fluorescence or colorimetric readouts, no light source or camera needed

> [!QUESTION] Open question
> At what scale/complexity does EIS data require machine learning vs simple threshold-based classification? The Thamwarokun paper uses a single cut-off value. For more complex analyte mixtures or heterozygous genotype discrimination, is ML required?

## Sources Informing This Page

- [[sources/thamwarokun-2023-eis-alpha-thal-spce|Thamwarokun et al. (~2023)]] — EIS for α-thal SEA deletion, optimal frequency (0.58 Hz), Rct vs -Z″ comparison, POC parameter specification
- [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis|Punter-Villagrasa et al. (2015)]] — EIS for hematocrit/anemia detection, 33 kHz single-frequency, RBC bulk physical model, hardware architecture
