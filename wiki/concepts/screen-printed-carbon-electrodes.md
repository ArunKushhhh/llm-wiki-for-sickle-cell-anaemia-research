---
title: "Screen-Printed Carbon Electrodes (SPCEs)"
type: concept
tags: [spce, electrodes, biosensor, carbon, screen-printing, disposable, pet-substrate]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["electrical-impedance-spectroscopy"], ["hoechst-33258"], ["point-of-care-diagnostics"]]
---

# Screen-Printed Carbon Electrodes (SPCEs)

## What They Are

Screen-printed carbon electrodes (SPCEs) are disposable, mass-producible electrochemical sensors fabricated by screen-printing conductive carbon paste onto an inert substrate (commonly PET, paper, or ceramic). They form a complete 3-electrode system on a flat surface.

## Why SPCEs for POC Biosensing

| Property | Relevance |
|----------|-----------|
| Low cost | Enables single-use disposal — no cross-contamination |
| High chemical stability | Inert in most biological buffers |
| Rich surface chemistry | Carbon surfaces are easily functionalized |
| Electrocatalytic activity | Broad range of redox reactions supported |
| Mass-producible | Consistent batch-to-batch characteristics |
| Disposable | No cleaning required between samples |
| Portable | Used with handheld potentiostats (e.g., PalmSens4) |

## Fabrication (from [[sources/thamwarokun-2023-eis-alpha-thal-spce]])

The Thamwarokun study custom-fabricated SPCEs with these specifications:

- **Substrate:** PET (polyethylene terephthalate)
- **Dimensions:** 12 mm wide × 25 mm tall
- **Working electrode (WE):** Carbon paste, active area = 12.57 mm²
- **Counter electrode (CE):** Carbon paste, active area = 15.70 mm²
- **Reference electrode (RE):** Ag/AgCl (60:40 ratio)
- **Layer order:**
  1. Carbon paste (WE + CE) — baked 60°C/5 min
  2. Ag/AgCl (RE) — baked 60°C/5 min
  3. Insulator paste — cured 120°C/5 min
- **Design tool:** Adobe Illustrator

**Cleaning protocol:** CV in 0.1M PBS (pH 7.4), 0–1.0 V, 6 cycles, 100 mV/s scan rate  
**Instrument:** PalmSens4 potentiostat + PSTrace 5 software

## Three-Electrode System

SPCEs implement the standard 3-electrode electrochemical cell on a single flat chip:
- **Working electrode (WE):** Where the sensing reaction occurs; carbon
- **Reference electrode (RE):** Fixed potential reference; Ag/AgCl
- **Counter electrode (CE):** Completes the circuit; carbon

## SPCE vs Other Electrode Platforms

| Platform | Pros | Cons |
|----------|------|------|
| Glassy carbon electrode (GCE) | High purity, reproducible | Expensive, requires polishing, reusable → contamination risk |
| Gold electrode | Easy thiol functionalization | High cost, not mass-producible |
| SPCE | Disposable, cheap, mass-produced | More variable than GCE; surface roughness |
| PCB-based electrode | Extremely cheap, scalable | Less electrochemically active |
| Graphene-modified SPCE | Higher conductivity, better sensitivity | More complex fabrication |

> [!TIP] Commercial SPCEs
> Dropsens (Metrohm), Zullig, and other vendors supply off-the-shelf SPCEs. Custom fabrication (as in Thamwarokun) allows optimization but adds complexity.

> [!QUESTION] Open question
> How much does SPCE fabrication variability (run-to-run batch differences) affect EIS reproducibility in clinical settings? The Thamwarokun paper does not report inter-batch CV for fabricated electrodes.

## Sources Informing This Page

- [[sources/thamwarokun-2023-eis-alpha-thal-spce|Thamwarokun et al. (~2023)]] — Complete SPCE fabrication protocol; electrode geometry; use in clinical EIS for α-thalassemia detection
