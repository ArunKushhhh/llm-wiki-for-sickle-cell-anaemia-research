---
title: "Alpha-Thalassemia"
type: concept
tags: [alpha-thalassemia, hemoglobinopathy, sea-deletion, hb-barts, genetics, globin, sickle-cell]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["electrical-impedance-spectroscopy"], ["screen-printed-carbon-electrodes"], ["point-of-care-diagnostics"]]
---

# Alpha-Thalassemia

## Disease Overview

Alpha-thalassemia is an inherited blood disorder caused by mutations or deletions in one or more of the four **α-globin genes** (located on chromosome 16; two genes per chromosomal copy: HBA1 and HBA2). It is one of the most common hemoglobinopathies in the world, with the highest prevalence in Southeast Asia, sub-Saharan Africa, and the Mediterranean.

**Normal genotype:** αα/αα (four functional α-globin genes)

## Genotype–Phenotype Spectrum

| Genotype | Name | Clinical Severity |
|----------|------|------------------|
| −α/αα | Silent carrier (α-thal-2 trait) | Asymptomatic; MCV slightly low |
| −α/−α or −−/αα | α-Thalassemia trait (minor) | Mild microcytic anemia |
| −−/−α | HbH disease | Moderate hemolytic anemia; splenomegaly |
| **−−/−−** | **Hb Bart's hydrops fetalis** | **Fatal in utero or shortly after birth** |

## The SEA Deletion (−−<sup>SEA</sup>)

The **SEA deletion** (Southeast Asian deletion) is a ~20.5 kb deletion affecting both α-globin genes on a single chromosome. It is the most clinically significant α-thalassemia deletion in Southeast Asia.

**Key facts:**
- A carrier (−−<sup>SEA</sup>/αα) has one normal chromosome and one with both genes deleted
- Two SEA carriers mating have a **25% risk** of producing a Hb Bart's hydrops fetalis baby (−−/−−)
- Hb Bart's is the most severe form: fetal hemoglobin substituted entirely by Hb Bart's (γ4 tetramers) which has extremely high O2 affinity → tissue hypoxia → fetal death

> [!IMPORTANT] Why carrier detection matters
> The only current management is prenatal screening and genetic counseling. Identifying SEA carrier couples before pregnancy is the primary prevention strategy. This makes sensitive, affordable, rapid carrier detection a public health priority — directly motivating biosensor research.

## Current Diagnostic Methods

| Method | Sensitivity | Cost | Time | Limitation |
|--------|-------------|------|------|------------|
| PCR + gel electrophoresis | High | ~$40 | 2–4 hrs | Equipment-intensive; requires UV imaging |
| Real-time PCR | Very high | High | 1–2 hrs | Expensive instrument |
| QCM-based biosensor (Chomean et al., 2010) | High | Moderate | Moderate | Requires probe immobilization |
| **EIS + SPCEs (Thamwarokun ~2023)** | **100%** | **~$2** | **1.5 hr PCR + 1 min EIS** | Specificity 88.2%; needs isothermal PCR for full POC |

## Hematological Screening Trigger

Carriers are often first flagged by routine CBC showing:
- **MCV < 80 fL** (microcytic red blood cells)
- Hypochromic red cells

The Thamwarokun study used MCV < 80 fL as the enrolment criterion for their 81-sample clinical cohort — a practical real-world triage filter.

## Epidemiology (Thailand context)

- α-Thalassemia affects a significant proportion of Northeast Thai newborns
- Thailand has active national prevention programs tracking prevalence over decades
- SEA deletion is the dominant form in Thailand, Myanmar, Laos, Vietnam, and southern China

> [!QUESTION] Open question
> How does SEA deletion affect the electrical impedance signature of whole blood or red blood cells directly (without PCR amplification)? Direct impedance profiling of cells rather than extracted DNA is an unexplored but potentially powerful POC approach.

## Relation to Sickle Cell Anemia

Alpha-thalassemia and [[sickle-cell-anemia]] are both hemoglobinopathies but mechanistically distinct:
- α-Thal: reduced quantity of α-globin chains
- SCA: structurally mutant β-globin (HbS) leading to polymerization
- They can co-exist: α-thal trait can actually *ameliorate* HbSS severity by reducing HbS concentration per cell

## Sources Informing This Page

- [[sources/thamwarokun-2023-eis-alpha-thal-spce|Thamwarokun et al. (~2023)]] — EIS biosensor for SEA deletion; disease prevalence and clinical management context
