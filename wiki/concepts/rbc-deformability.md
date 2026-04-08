---
title: "RBC Deformability"
type: concept
tags: [rbc, deformability, rheology, stiffness, microcirculation, sickle-cell, thalassemia, microfluidics]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["sickle-cell-disease"], ["rbc-electrical-model"], ["electrical-impedance-spectroscopy"], ["hematocrit-impedance-relationship"], ["microfluidics"]]
---

# RBC Deformability

## What It Is

Red blood cell (RBC) deformability is the ability of RBCs to change shape reversibly in response to external forces — specifically to squeeze through microcapillaries (3–8 µm) that are smaller than their resting diameter (~8 µm). It is a critical biophysical property for normal microcirculation and oxygen delivery.

**Three determinants of RBC deformability:**
1. **Surface area–to–volume ratio** — higher ratio → more membrane excess → easier deformation
2. **Membrane cytoskeletal integrity** — spectrin, ankyrin, Band 3, protein 4.2 network
3. **Cytoplasmic viscosity** — governed by intracellular hemoglobin concentration and state

Disruption of any of these leads to **increased stiffness / decreased deformability** → impaired microcirculation.

## Disease-Related Deformability Changes

| Condition | Primary mechanism | Deformability change |
|-----------|------------------|---------------------|
| **Sickle cell disease (HbSS)** | HbS polymerization → rigid cytoskeleton | ↓↓ Severely reduced |
| **Hereditary spherocytosis (HS)** | Spectrin/ankyrin mutations → membrane loss | ↓ Reduced |
| **Malaria (P. falciparum)** | Parasite antigens stiffen membrane | ↓ Severely reduced |
| **α-Thalassemia** | Membrane damage from α/β globin imbalance | ↓ Mildly reduced |
| **Iron deficiency anemia** | Microcytic RBCs, altered membrane | ↓ Mildly reduced |
| **Storage lesion (banked RBCs)** | Progressive stiffening during storage | ↓ Time-dependent |

## Measurement Techniques

### Single-Cell Methods (Lab-Intensive)
- **AFM (atomic force microscopy):** Measures elastic modulus at nm resolution; requires specialized equipment and expertise
- **Optical tweezers:** Stretches individual cells with laser; extremely precise but low throughput
- **Micropipette aspiration:** Measures cell cortical tension; classical but slow

### Bulk Methods (Higher Throughput)
- **Ektacytometry:** Shear flow + laser diffraction → elongation index curve vs osmolality
- **Cell transit analyzer (CTA):** Cells transit through narrow pores; time-based metric
- **Microfluidic systems with imaging:** Transit through capillary networks; requires high-speed camera

### EIS-Based Methods (Imaging-Free)
- **Microfluidic impedance (Man et al. 2021):** Cells occlude channels → block current → REI increases. **Imaging not required for routine use.**

## The REI — A New EIS Deformability Metric

From [[sources/man-2021-microfluidic-eis-scd-microvascular]]:

**RBC Electrical Impedance Index (REI)** = cumulative % impedance change across 3–10 µm micropillar arrays after sample perfusion

```
REI = Σ [(I₂ᵢ - I₁ᵢ) / I₁ᵢ] × 100%
```

- Higher REI → more capillary occlusion → lower deformability
- Validated against ROI (imaging-based occlusion count): PCC = 0.946–0.987
- Discriminates SCD from healthy at p<0.05 (N=12 HbSS vs N=5 healthy)
- Responds to as little as **1% stiff RBCs** in a healthy background

> [!TIP] REI enables POC adaptation
> By replacing high-resolution microscopy (needed for ROI) with electrical impedance (REI), the microfluidic deformability assay becomes compatible with POC hardware — portable impedance analyzer + disposable chip, no camera needed.

## Connection to Research Focus

Deformability is the **bridge between molecular mutation and macroscopic impedance signal** in hemoglobinopathies:

```
HbS mutation → polymerization → ↑ cytoplasmic viscosity + ↑ membrane rigidity
            → ↓ deformability → cells can't deform through capillaries
            → mechanical occlusion → REI ↑ (detectable by EIS)
```

This chain means that **EIS can detect the functional consequence of a genetic mutation** without genotyping — a profound simplification for POC diagnostics. The limitation is specificity: any condition reducing RBC deformability (malaria, HS, storage lesion) would also raise REI.

## Sources Informing This Page

- [[sources/man-2021-microfluidic-eis-scd-microvascular|Man et al. (2021)]] — REI definition, validation against ROI, SCD/HS clinical data, device design
