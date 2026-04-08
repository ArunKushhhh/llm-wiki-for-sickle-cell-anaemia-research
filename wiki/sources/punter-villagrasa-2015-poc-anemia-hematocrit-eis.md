---
title: "Instantaneous Low-Cost POC Anemia Detection via Hematocrit Impedance"
type: source
tags: [anemia, hematocrit, impedance, whole-blood, poc, spce, gold-electrode, rbc, eis, low-frequency]
created: 2026-04-09
updated: 2026-04-09
related: [["electrical-impedance-spectroscopy"], ["point-of-care-diagnostics"], ["screen-printed-carbon-electrodes"], ["hematocrit-impedance-relationship"], ["anemia"], ["rbc-electrical-model"]]
---

# Instantaneous Low-Cost POC Anemia Detection via Hematocrit Impedance

## Citation

**Title:** An Instantaneous Low-Cost Point-of-Care Anemia Detection Device  
**Authors:** Jordi Punter-Villagrasa, Jordi Cid, Jordi Colomer-Farrarons, Ivan Rodriguez-Villarreal, Pere Ll. Miribel-Catala  
**Institution:** Universitat de Barcelona / Hospital Clínic, Barcelona, Spain  
**Journal:** *Sensors* 2015, **15**, 4564–4577  
**DOI:** open access, MDPI  
**Year:** 2015  
**Keywords:** whole blood, hematocrit, impedance analysis, electronics, point-of-care

Raw source: `[[raw/An Instantaneous Low-Cost Point-of-Care Anemia Detection Device.pdf]]`

---

## Abstract / TL;DR

This paper presents a compact, portable, low-cost (<€10 electronics) POC device that detects anemia by measuring hematocrit directly from a 50 µL whole blood drop via electrical impedance at a single frequency (33 kHz). The system uses a commercial disposable gold screen-printed 3-electrode sensor (Dropsens C223AT), a custom analog circuit (Wien bridge oscillator + potentiostat + RMS-to-DC converter), and achieves: Pearson's r = −0.96, accuracy error = 2.83%, mean CV = 2.57% across 24 clinical blood samples. It gives an instantaneous result (milliseconds), requires no reagents or optical components, and is fully battery-powered (300 mWh).

---

## Key Contributions

- Translates the **hematocrit–impedance relationship** into a fully integrated, sub-€10 hardware device — the first compact realization of prior feasibility work from the same group
- Operates at a **single fixed frequency (33 kHz)** — eliminates the need for a frequency analyzer, dramatically reducing complexity vs. the prior prototype (which used a full-spectrum FRA + FPGA platform)
- Demonstrates that **low-frequency EIS directly measures RBC volume fraction** without any DNA extraction, PCR, labeling, or reagents — pure physical/electrical measurement
- Validates on **24 real clinical blood samples** (HCT range 14.2%–50.6%) from Hospital Clínic, Barcelona — anemia-relevant range fully covered
- Positions the device as **instantaneous** (millisecond response) vs. existing POC anemia devices (AnemiaCheck, STAT-Site, HemoPoint H2) which are slower
- Establishes a **complete hardware architecture reference:** Wien bridge oscillator → potentiostat → transimpedance amplifier → RMS-to-DC converter (AD8436) → DC voltage output ∝ 1/HCT

---

## Key Claims and Evidence

| Claim | Evidence |
|-------|----------|
| Impedance at 33 kHz correlates with hematocrit | Pearson r = −0.96, r² = 0.9272 on 24 clinical samples |
| Accuracy competitive with commercial POC | Accuracy error 2.83%; CV 2.57% (all < 5% per clinical QC standards) |
| System is low-cost | Electronics BOM < €10; sensor = Dropsens C223AT (commercial, disposable) |
| System is instantaneous | Measurement time: milliseconds vs. hours for CBC |
| Higher HCT → lower VRMS | Inverse relationship: more RBCs → higher impedance → transimpedance output lower |
| 50 µL capillary sample sufficient | Compatible with fingerprick — no venipuncture needed |
| Single-frequency sufficient | 33 kHz chosen per prior characterization [ref 27]; full spectrum not needed |

---

## Physical Mechanism — Why Impedance Detects Hematocrit

This is the **key scientific insight** of the paper, and it is directly relevant to the broader research focus:

### RBC Electrical Model

Red blood cells (RBCs) are modelled as:
- **Extracellular medium (RE):** Resistive ionic solution
- **Cell membrane (CM ∥ RM):** Capacitor in parallel with membrane resistance
- **Intracellular medium (RI):** Resistive cytoplasm

### Frequency-Dependent Behavior

At **low frequencies (up to ~100 kHz):**
- Current cannot penetrate the insulating cell membrane
- All current flows **around the RBCs** through the extracellular medium (RE path)
- More RBCs = longer, more tortuous path for current = **higher impedance**
- Therefore: **impedance ∝ hematocrit** at low frequencies

At **high frequencies:**
- Current penetrates the membrane and flows through intracellular fluid too
- Impedance becomes less sensitive to cell volume fraction
- Loses the hematocrit-specific signal

> [!IMPORTANT] Critical insight for research focus
> The hematocrit–impedance relationship is a **bulk physical measurement of RBC volume fraction**, not a molecular/chemical measurement. This is fundamentally different from the Thamwarokun EIS approach (which measures DNA blocking a surface). Here, the signal arises from the **dielectric properties of suspended cells**. This opens the question: can the same principle discriminate *abnormal RBCs* (e.g., HbS sickle cells with altered morphology) from normal RBCs, not just count them?

---

## Methodology

**Sensing:**
- Electrode: Dropsens C223AT — commercial gold screen-printed 3-electrode, 1.6 mm diameter WE
- Sample volume: 50 µL whole blood (applied by pipette)
- Measurement: Single-frequency impedance at **33 kHz**

**Electronics architecture:**
1. **Oscillator:** Wien bridge (AD8066 JFET op-amp) → stable sinusoidal AC voltage (VCELL)
2. **Potentiostat:** Drives VCELL to WE; tracks solution potential at CE
3. **Transimpedance amplifier (AT):** Converts ICELL to voltage (VOUT) via RSENSE
4. **RMS-to-DC converter:** AD8436 (Analog Devices) → DC voltage VRMS proportional to magnitude of ICELL
5. **Output:** VRMS (mV) — inversely proportional to HCT. Higher HCT = lower VRMS.
6. **Readout:** LabVIEW interface via NI USB-6361 DAQ (lab validation only; production could use LCD, USB, or wireless)

**Total power consumption:** 300 mWh → long battery life, fully mobile

**Sample preparation:**
- 4 hospitalized patients at Hospital Clínic, Barcelona
- Blood centrifuged → RBCs separated from plasma → reconstituted at 24 different HCT levels (14.2%–50.6%)
- Ground truth: CBC by ABX Micros 60 hematology analyzer (Horiba)

---

## Results Summary

| Metric | Value |
|--------|-------|
| Pearson r (VRMS vs HCT) | −0.96 |
| Coefficient of determination (r²) | 0.9272 |
| Accuracy error | 2.83% HCT |
| Mean coefficient of variation | 2.57% |
| Maximum CV in any sample | < 5% |
| HCT range validated | 14.2% – 50.6% |

VRMS decreases from ~1726 mV (HCT 14.2%, severe anemia) to ~490 mV (HCT 50.6%, near-normal), giving a ~3.5× dynamic range in voltage across the clinically relevant HCT spectrum.

---

## Comparison to Prior Work (from the paper)

| System | Approach | Speed | Cost |
|--------|----------|-------|------|
| **This device** | Single-freq EIS, 33 kHz | Milliseconds | < €10 electronics |
| Prior group prototype [ref 27] | Full-spectrum FRA (DLIA + FPGA) | Slower | Much higher |
| AnemiaCheck (Express Diagnostics) | Similar POC | Slower | Commercial |
| STAT-Site (Stanbio Lab) | Similar POC | Slower | Commercial |
| HemoPoint H2 (Alere) | Similar POC | Slower | Commercial |
| Tyburski et al. color-based test | Colorimetric visual readout | Slow (biochemical reaction) | Low | Visual interpretation errors; low resolution |

---

## Limitations and Open Questions

> [!WARNING] Small and controlled sample
> Only 24 samples from 4 patients. Samples were generated by *centrifugation + reconstitution* — not true patient samples at measured HCT. This controls for confounders but may not reflect real-world variability (different RBC sizes, shapes, protein content, disease states).

- **No disease-state discrimination:** Detects anemia (low HCT/Hb) but cannot distinguish *cause* — sickle cell, thalassemia, iron deficiency, chronic disease — all present as low HCT
- **Gold electrode sensor:** C223AT uses gold, not carbon. Gold is more expensive than carbon-paste SPCEs. For mass-scale deployment, carbon-based SPCEs (as in Thamwarokun) are cheaper
- **Hematocrit and hemoglobin correlation assumed:** HCT and Hb correlate well in most cases but diverge in some conditions (microcytosis, macrocytosis, spherocytosis). The device measures HCT, not Hb directly.
- **Temperature dependence not discussed:** Blood impedance changes with temperature; no temperature correction reported
- **No validation for sickle cell or thalassemia samples specifically:** A key open question for this research focus

> [!QUESTION] Can the same 33 kHz single-frequency approach detect RBC morphological abnormalities?
> Sickle RBCs have abnormal shape (crescent vs biconcave disk), altered membrane properties, and higher internal viscosity. Would their impedance at 33 kHz differ from normal RBCs at the same HCT? If so, this device architecture could potentially discriminate disease states, not just count cells.

---

## Connection to Research Focus

This paper is **adjacent but important** to the core research focus. Key connections:

1. **Physical mechanism for RBC impedance sensing** — explains *why* low-frequency EIS is sensitive to RBC volume, providing the biophysical basis for potential extension to hemoglobin variant discrimination
2. **Hardware architecture reference** — the Wien oscillator + potentiostat + transimpedance + RMS-to-DC chain is a clean, low-cost, low-power hardware template applicable to the target diagnostic device
3. **Anemia as downstream consequence** — sickle cell anemia and thalassemia both cause anemia; this device detects the downstream effect (low HCT), while the research focus targets root cause (hemoglobin variant). Both layers are needed for a complete diagnostic system.
4. **POC hardware cost benchmark** — < €10 electronics sets a strong target for BOM cost in embedded system design
5. **Single-frequency approach validated** — confirms that full impedance sweeps are not always necessary; 33 kHz (for HCT) and 0.58 Hz ([[sources/thamwarokun-2023-eis-alpha-thal-spce]], for DNA-level detection) operate at very different frequencies for different purposes

> [!NOTE] Complementary, not competitive
> The Thamwarokun paper and this paper address different diagnostic layers: DNA-level genotyping (carrier detection) vs. blood-level phenotyping (anemia severity). A complete hemoglobinopathy POC device would ideally do both.

## Related Wiki Pages

- [[concepts/electrical-impedance-spectroscopy]] — shared framework; now has two applications: DNA surface blocking (0.58 Hz) vs. RBC bulk measurement (33 kHz)
- [[concepts/point-of-care-diagnostics]] — ASSURED principles; hardware BOM cost reference; battery-life discussion
- [[concepts/screen-printed-carbon-electrodes]] — this paper uses gold SPE (Dropsens C223AT), a relevant comparison
- [[concepts/hematocrit-impedance-relationship]] — new concept page needed; this paper is its primary source
- [[concepts/anemia]] — new concept page needed; disease context and prevalence
- [[concepts/rbc-electrical-model]] — new concept page needed; the passive RC network model for cells
- [[sources/thamwarokun-2023-eis-alpha-thal-spce]] — contrast in EIS application: DNA detection vs. cell counting
