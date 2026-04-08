---
title: "Microfluidics for Blood Diagnostics"
type: concept
tags: [microfluidics, lab-on-chip, pdms, micropillar, capillary-network, poc, blood, rbc]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["electrical-impedance-spectroscopy"], ["rbc-deformability"], ["sickle-cell-disease"], ["point-of-care-diagnostics"], ["screen-printed-carbon-electrodes"]]
---

# Microfluidics for Blood Diagnostics

## What It Is

Microfluidics involves manipulation of fluids at the micron scale (channels typically 1–1000 µm), enabling precise control of small sample volumes. In blood diagnostics, microfluidic devices can:
- Mimic physiological vessel geometries (capillaries: 3–10 µm)
- Process µL-scale blood samples
- Integrate sensors (impedance electrodes, optical detectors) directly
- Enable single-chip, disposable, POC-ready platforms

## Architectures Relevant to RBC Assessment

### Micropillar/Capillary Network Arrays
Used in [[sources/man-2021-microfluidic-eis-scd-microvascular]]:
- Arrays of pillars create channels that range from 3–12 µm
- RBCs must deform to pass through
- Stiff/rigid cells (SCD, HS, malaria) get trapped → countable via imaging or detectable via impedance
- Integrated gold electrodes on either side of each array measure impedance change before/after perfusion

**Design choices that matter:**
- Channel width determines which diseases/conditions are tested (3 µm catches most sickle cells; 10 µm traps only large aggregates)
- Bypass pathways prevent upstream clogging
- Disposable single-use chips prevent cross-contamination

### Ektacytometry / Shear-Flow Systems
- Cells stretched under shear flow; deformation measured optically
- High throughput; requires laser diffractometer
- Not easily miniaturized for POC

### Droplet Microfluidics
- Encapsulates single cells in droplets; enables single-cell assays at high throughput
- Not yet applied to SCD diagnostics at POC scale

## Electrode Integration for Impedance Readout

The key innovation in the Man et al. design is pairing each micropillar array with **sputtered gold electrodes** that measure impedance **across the array**:
- Pre-perfusion: open channels → low impedance (current flows freely)
- Post-perfusion: some channels blocked by stiff RBCs → higher impedance (current path restricted)
- ΔZ is proportional to the number of blocked channels → REI

**Operating frequency: 10 kHz** — chosen to sense channel occlusion (macroscopic channel blockage), not intracellular properties.

Contrast with [[concepts/hematocrit-impedance-relationship]] (33 kHz, bulk extracellular path) and DNA EIS (0.58 Hz, surface blocking) — all three use different frequencies for different physical phenomena.

## Fabrication

Standard microfluidic fabrication:
- **PDMS (polydimethylsiloxane)** soft lithography on photolithographic molds
- **Substrate:** Glass or silicon wafer
- **Electrodes:** Sputtered gold (Ti/Au adhesion layer)
- **Bonding:** Plasma treatment + PDMS-to-glass bonding
- **Device size:** Compact, portable (see photograph in Man et al.)

## POC Translation Challenges

> [!WARNING] Fabrication complexity is a barrier
> Current microfluidic devices require cleanroom photolithography and PDMS molding. This is incompatible with large-scale manufacturing at the cost point needed for rural/resource-constrained POC deployment.

**Alternatives in development:**
- **Paper microfluidics (lateral flow):** Ultra-cheap; limited channel geometry control
- **Injection-molded thermoplastics (COC, PMMA):** Mass-manufacturable at < $1/chip; geometrically precise
- **3D printing:** Emerging; resolution still limited for 3–10 µm features

> [!QUESTION] Can the Man et al. capillary impedance principle be implemented in a thermoplastic injection-molded chip?
> This would dramatically reduce per-device cost and enable mass manufacturing compatible with the research focus's affordability requirement.

## Processing Time & Sample Volume

From [[sources/man-2021-microfluidic-eis-scd-microvascular]]:
- Sample volume: blood at 20% HCT (diluted from clinical blood)
- Perfusion time: 20 min + 20 min PBS wash
- Data acquisition: < 5 min

> [!NOTE] 40 min total per sample limits throughput
> For a true POC screening tool, this would need to be reduced to < 10 min. Isothermal amplification analogy: the PCR bottleneck in the genotyping pipeline has a direct equivalent here in the perfusion time.

## Sources Informing This Page

- [[sources/man-2021-microfluidic-eis-scd-microvascular|Man et al. (2021)]] — micropillar array design, gold electrode integration, 10 kHz measurement, PDMS fabrication
