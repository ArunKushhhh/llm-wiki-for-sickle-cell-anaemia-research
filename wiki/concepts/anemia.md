---
title: "Anemia"
type: concept
tags: [anemia, hemoglobin, hematocrit, rbc, who, iron-deficiency, sickle-cell, thalassemia, poc]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["alpha-thalassemia"], ["hematocrit-impedance-relationship"], ["point-of-care-diagnostics"], ["rbc-electrical-model"]]
---

# Anemia

## WHO Definition

Anemia is defined as a condition where the number of red blood cells (RBCs) or their oxygen-carrying capacity is **insufficient to meet physiological needs**. The primary clinical indicator is low hemoglobin (Hb) concentration; hematocrit (HCT) is also a reliable secondary indicator.

**WHO thresholds for anemia:**

| Population group | Hb threshold |
|-----------------|-------------|
| Children 6–59 months | < 11.0 g/dL |
| Non-pregnant women | < 12.0 g/dL |
| Pregnant women | < 11.0 g/dL |
| Men | < 13.0 g/dL |

## Epidemiology

- **~2 billion people** affected globally (~30% of world population)
- Highest prevalence: **Africa (67.6%), South-East Asia (65.5%)**
- Eastern Mediterranean: 46%
- Most vulnerable: pregnant women and children

## Causes Relevant to Research Focus

| Cause | Mechanism | Relation to research |
|-------|-----------|---------------------|
| **Sickle Cell Anemia (SCA)** | HbS polymerization → hemolytic anemia; reduced RBC lifespan | Core research target |
| **Thalassemia** | Reduced globin synthesis → hypochromic microcytic anemia | Core research target — see [[concepts/alpha-thalassemia]] |
| Iron deficiency | Reduced Hb synthesis | Most common cause globally; not a research focus |
| Chronic kidney disease | Reduced EPO | Not a research focus |
| Chemotherapy | Bone marrow suppression | Not a research focus |
| Malnutrition | Multiple mechanisms | Common co-morbidity in target populations |

> [!NOTE] Anemia as downstream signal
> In hemoglobinopathies (SCA, thalassemia), anemia is the *consequence* of a genetic mutation, not the root cause. Detecting anemia with HCT measurement (as in [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis]]) reveals the downstream effect but not the specific mutation. Genotyping (as in [[sources/thamwarokun-2023-eis-alpha-thal-spce]]) is needed to identify the specific condition.

## HCT as a Diagnostic Marker

- **HCT (%)** = fraction of blood volume occupied by RBCs
- Correlates closely with Hb in most conditions
- Diverges in: microcytosis (small cells), macrocytosis (large cells), spherocytosis
- Can be measured directly by impedance (see [[concepts/hematocrit-impedance-relationship]]) or calculated from CBC

## Current Diagnostic Standard vs POC

| Method | HCT accuracy | Speed | Cost | Setting |
|--------|-------------|-------|------|---------|
| Automated CBC (Advia 2120, etc.) | Very high | 1–2 hrs | High | Hospital lab |
| Microhematocrit centrifugation | High | 15–30 min | Low | Clinic |
| Commercial POC (AnemiaCheck, etc.) | Moderate | Minutes | Moderate | POC |
| **EIS device (Punter-Villagrasa 2015)** | **2.83% error** | **Milliseconds** | **< €10** | **POC / Field** |
| Colorimetric visual test (Tyburski) | Lower | Minutes | Very low | Self-test |

## Screening Trigger in Hemoglobinopathy Programs

In α-thalassemia screening (see [[concepts/alpha-thalassemia]]):
- **MCV < 80 fL** is the standard first-line trigger for further genetic testing
- Anemia detection (low HCT) is the clinical phenotype that routes patients to molecular diagnosis

## Sources Informing This Page

- [[sources/punter-villagrasa-2015-poc-anemia-hematocrit-eis|Punter-Villagrasa et al. (2015)]] — anemia epidemiology, causes, POC device design and validation
