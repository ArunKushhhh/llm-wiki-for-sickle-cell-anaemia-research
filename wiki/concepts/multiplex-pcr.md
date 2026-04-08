---
title: "Multiplex PCR (mPCR) in Biosensing"
type: concept
tags: [pcr, multiplex-pcr, mpcr, dna-amplification, primer-design, amplicon-size, gc-content]
created: 2026-04-09
updated: 2026-04-09
source_count: 1
related: [["electrical-impedance-spectroscopy"], ["hoechst-33258"], ["alpha-thalassemia"]]
---

# Multiplex PCR (mPCR) in Biosensing

## What It Is

Multiplex PCR (mPCR) is a variant of PCR that amplifies multiple DNA targets simultaneously in a single reaction, using multiple primer sets. In the context of EIS biosensing, mPCR is used as the upstream amplification step that generates dsDNA amplicons for electrochemical detection.

## Role in the EIS Biosensing Pipeline

```
Genomic DNA → mPCR amplification → dsDNA amplicons → H33258 binding → EIS measurement → Diagnosis
```

The mPCR step serves two functions:
1. **Amplification:** Converts low-abundance target DNA into detectable quantities
2. **Discrimination:** Primer design determines which sequences are amplified — this is where specificity is established

## Key Design Parameters (from [[sources/thamwarokun-2023-eis-alpha-thal-spce]])

### Amplicon Size — Critical for EIS Sensitivity

> [!IMPORTANT] Shorter amplicons = stronger EIS signal
> Primer set 1 (~242 bp) outperformed sets producing 282 bp, 435 bp, and 700 bp amplicons. Shorter fragments bind H33258 more efficiently and block the electrode surface more densely, increasing Rct.
> **Design rule:** Minimize amplicon length (while maintaining primer specificity) when coupling mPCR with H33258-based EIS.

### GC Content
- Thamwarokun primers: 35–70% GC content (range 39.13–68.42%)
- GC content affects melting temperature and primer stability
- No secondary structure in primers (verified computationally)
- GC content of amplicon affects how many H33258 molecules bind (H33258 prefers AT-rich minor grooves)

### Protocol (Thamwarokun study)
- Volume: 20 µL per reaction
- Master mix: GoTaq Master Mix (Promega) 2x, 10 µL
- Template: 100 ng genomic DNA
- Thermocycling: 35 cycles × (95°C/30s, 63°C/30s, 72°C/30s)
- Verification: 1.5% agarose gel + UV
- Design tool: Primer3 (sequence AY207443 for α-globin)

## Limitations as a POC Component

| Issue | Impact |
|-------|--------|
| Requires thermocycler | Not field-deployable without power + instrument |
| ~1.5 hr amplification time | Total assay time ~1.5 hr + 1 min EIS |
| Non-specific amplification | Can generate spurious signal in H33258 EIS |
| Primer dimer formation | Causes false positives; NTC control required |

## Isothermal Alternatives
For true POC deployment, the authors of [[sources/thamwarokun-2023-eis-alpha-thal-spce]] suggest:
- **LAMP** (Loop-mediated isothermal amplification): ~65°C fixed temperature, ~30–60 min
- **RPA** (Recombinase polymerase amplification): ~37°C, ~20 min, very low energy
Both have been successfully coupled with graphene/SPCE EIS sensors in other contexts (e.g., *Mycobacterium tuberculosis*, *Vibrio parahaemolyticus*).

## Sources Informing This Page

- [[sources/thamwarokun-2023-eis-alpha-thal-spce|Thamwarokun et al. (~2023)]] — mPCR for α-thal SEA deletion; primer design parameters; amplicon size effect on EIS signal
