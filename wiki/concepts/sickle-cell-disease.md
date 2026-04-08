---
title: "Sickle Cell Disease (SCD)"
type: concept
tags: [sickle-cell, hbs, hemoglobinopathy, vaso-occlusion, deformability, rbc, polymerization, anemia, poc]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["alpha-thalassemia"], ["anemia"], ["rbc-electrical-model"], ["rbc-deformability"], ["electrical-impedance-spectroscopy"], ["hematocrit-impedance-relationship"]]
---

# Sickle Cell Disease (SCD)

## Disease Overview

Sickle cell disease (SCD) is a group of inherited hemoglobin disorders caused by a point mutation in the β-globin gene (GAG → GTG at codon 6) resulting in the substitution of glutamic acid with valine in the hemoglobin β-chain, producing **sickle hemoglobin (HbS)**. The most severe form, **HbSS** (homozygous sickle cell anemia), produces only HbS.

**Genetic basis:**
- Normal: HbAA (β^A β^A)
- Carrier (trait): HbAS (β^A β^S) — usually asymptomatic
- Disease: **HbSS** (β^S β^S) — sickle cell anemia (most severe)
- Compound: HbSC, HbSβ-thal (also clinically significant)

## Pathophysiology — The HbS Polymerization Cascade

Under **deoxygenation**, HbS molecules polymerize into rigid helical fibers. This triggers a cascade:

```
Deoxygenation → HbS polymerization → RBC distortion (sickle shape)
             → Membrane rigidity ↑ → Deformability ↓
             → Adhesiveness ↑ → Microvascular occlusion (vaso-occlusion)
             → Hemolysis → Anemia + reticulocytosis + elevated LDH
```

Key biophysical changes in HbSS RBCs:
- **Increased membrane rigidity** → cells can't squeeze through 3–8 µm capillaries
- **Distorted morphology** (crescent/sickle shapes instead of biconcave disc)
- **Elevated cytoplasmic viscosity** due to HbS polymer networks
- **Increased surface adhesion** to endothelium and other blood cells

## Clinical Manifestations

- **Vaso-occlusive crisis (VOC):** Pain episodes from microvascular blockage
- **Hemolytic anemia:** RBC destruction → low Hb, high unconjugated bilirubin, high LDH, reticulocytosis
- **Acute chest syndrome (ACS):** Severe pulmonary event; leading cause of death
- **Stroke:** Cerebrovascular occlusion in large vessels
- **Organ damage:** Spleen, kidney, bone, lung — progressive from chronic ischemia

## Hemolytic Biomarkers

| Biomarker | Normal range | Elevated in SCD because... |
|-----------|-------------|---------------------------|
| LDH (lactate dehydrogenase) | < 250 U/L | Released from lysed RBCs |
| Absolute Reticulocyte Count (ARC) | < 100 × 10⁹/L | Bone marrow response to hemolysis |
| Unconjugated bilirubin | < 1.2 mg/dL | Heme catabolism product |

> [!IMPORTANT] REI and LDH correlation established
> [[sources/man-2021-microfluidic-eis-scd-microvascular]] shows that the **RBC Electrical Impedance Index (REI)** from microfluidic impedance measurement correlates with LDH levels and ARCs across SCD patients. This is key: it means impedance-based functional assessment reflects the same disease severity axis as standard haematology biomarkers.

## Current Treatments

| Treatment | Mechanism | Effect on impedance biomarker |
|-----------|-----------|------------------------------|
| **Hydroxyurea (HU)** | Induces fetal hemoglobin (HbF) production; HbF inhibits HbS polymerization | ↓ ROI and REI toward healthy range |
| **Exchange transfusion** | Replaces sickle RBCs with healthy donor RBCs | ↓ ROI and REI (remaining sickle cells still occlude) |
| **Allogeneic HSCT** | Replaces hematopoietic stem cells; curative | Patient in Man et al.: ROI/REI near-normal post-transplant |
| **Gene therapy** | Corrects the β^S mutation in autologous HSC | Active research (Cure Sickle Cell Initiative) |

## EIS Discrimination of SCD RBCs — Evidence

From [[sources/man-2021-microfluidic-eis-scd-microvascular]]:

| Group | ROI (mean ± SD) | REI (mean ± SD) |
|-------|-----------------|-----------------|
| Healthy (n=5) | 8.02 ± 1.71% | 4.31 ± 1.25% |
| HbSS SCD (n=12) | 34.65 ± 21.99% | Significantly higher |
| Post-HSCT SCD patient | 10.08% | 2.44% (near-healthy) |

The impedance approach operates at **10 kHz**, through a microfluidic capillary network that forces RBCs through 3–12 µm channels. Stiff sickle cells fail to deform through these channels, blocking current and raising impedance.

## Relation to Alpha-Thalassemia

Alpha-thalassemia and sickle cell disease are distinct conditions that can co-occur:
- α-thalassemia trait **ameliorates HbSS severity** by reducing mean corpuscular Hb concentration (MCHC), making HbS polymerization less likely
- In populations where both are prevalent (sub-Saharan Africa, Middle East), the co-inheritance is clinically important

See also: [[concepts/alpha-thalassemia]]

## Open Questions

> [!QUESTION] What happens under deoxygenation?
> The Man et al. microfluidic study was done at ambient oxygen. HbS polymerizes much more aggressively under low pO₂. Adding a deoxygenation step (nitrogen flush, sodium metabisulfite) would likely greatly amplify the REI difference between SCD and healthy — and might reveal differences in HbAS trait vs HbAA that are invisible at ambient O₂.

> [!QUESTION] Can simplified bulk-blood EIS (no microfabrication) detect SCD-specific signatures?
> The microfluidic approach requires PDMS/silicon fabrication. A simpler disposable SPCE-based approach with optimized frequency and flow conditions might capture similar mechanical discrimination with lower manufacturing complexity.

## Sources Informing This Page

- [[sources/man-2021-microfluidic-eis-scd-microvascular|Man et al. (2021)]] — mechanism, clinical data, REI/ROI metrics, treatment stratification, hemolytic biomarker correlation
