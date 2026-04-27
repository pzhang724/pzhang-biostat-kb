---
title: "Pharmaverse"
type: entity
tags: [organization, r-package, clinical-data, cdisc, open-source]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# Pharmaverse

## Organization / Ecosystem

**Type**: Open-source R package ecosystem
**Repo**: https://pharmaverse.org
**Maintained by**: Cross-industry consortium (Roche, Pfizer, GSK, and others)
**Primary use**: End-to-end R-based clinical reporting pipeline following CDISC standards

### Overview

Pharmaverse is a curated collection of R packages designed to cover the full clinical data pipeline from raw EDC data through regulatory submission:

```
Raw EDC data
    ↓ {sdtm.oak}
SDTM datasets
    ↓ {admiral}
ADaM datasets
    ↓ TLG packages
Tables, Listings, Graphs (submission-ready)
```

The ecosystem enables pharmaceutical companies to replace SAS-based workflows with open-source R, while maintaining CDISC compliance and regulatory acceptability.

### Key Packages

| Package | Role |
|---------|------|
| [[sdtm.oak R Package]] | Raw EDC → SDTM datasets |
| `admiral` | SDTM → ADaM datasets |
| `pharmaverse.raw` | Example raw datasets for testing |
| `pharmaverse.stm` | Example SDTM datasets for reference |
| TLG packages | ADaM → submission tables/listings/graphs |

### Connections

- Contains: [[sdtm.oak R Package]]
- Related concept: [[CDISC SDTM]]
- Source: [[SDTM Programming in R using {sdtm.oak} Package]]
