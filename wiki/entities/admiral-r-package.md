---
title: "admiral R Package"
type: entity
tags: [r-package, adam, cdisc, pharmaverse, clinical-trials]
created: 2026-04-30
updated: 2026-04-30
sources: 2
---

# admiral R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("admiral")`  
**Repo**: github.com/pharmaverse/admiral  
**Maintained by**: Pharmaverse cross-industry community (Roche, GSK, Pfizer, and others)  
**Primary use**: Creating CDISC ADaM datasets from SDTM data in R

### Overview

`{admiral}` (ADaM in R Asset Library) is the ADaM layer of the [[Pharmaverse]] ecosystem. It provides modular building-block functions for deriving ADaM variables, flags, and datasets, following the CDISC ADaM standard. The design philosophy is transparency: users compose derivations explicitly rather than running a black-box automation.

### Extension Family

| Package | Therapeutic Area |
|---------|-----------------|
| `{admiralonco}` | Oncology |
| `{admiralophtha}` | Ophthalmology |
| `{admiralvaccine}` | Vaccines |
| `{admiralpeds}` | Pediatrics |
| `{admiralmetabolic}` | Metabolic diseases |
| `{admiralneuro}` | Neurology |
| `{admiralroche}`, `{admiralgsk}` | Company-specific plug-ins |

### Design Principles

1. **Usability**: comprehensive documentation with real-life examples; vignettes for common dataset types (ADSL, BDS, OCCDS)
2. **Simplicity**: functions have narrow purposes; avoid >10-argument functions; no multi-purpose overloading
3. **Findability**: consistent naming conventions; searchable website; functions grouped by purpose
4. **Readability**: tidyverse (dplyr) preferred over base R; shallow nesting; programming strategy enforced for all contributors

### When to Use

- Converting SDTM datasets to ADaM format for FDA/EMA submission
- Deriving analysis flags (SAFFL, MITTFL, ANL01FL), study days, age, duration variables
- Building ADSL, ADTTE, ADVS, ADLB, ADAE datasets in a traceable, auditable way

### Limitations

- Does not cover 100% of all ADaM derivations; study-specific derivations always remain
- TA extension packages may lag behind core release cadence

### Connections

- Implements: [[CDISC ADaM]]
- Part of: [[Pharmaverse]]
- Upstream: [[sdtm.oak R Package]] (SDTM input)
- Downstream: [[tern R Package]], [[chevron R Package]] (consume ADaM output)
- Source: [[ADaM in R Asset Library]]
