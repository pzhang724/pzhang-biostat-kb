---
title: "Pharmaverse"
aliases: ["Pharmaverse"]
type: entity
tags: [organization, r-package, clinical-data, cdisc, open-source]
created: 2026-04-27
updated: 2026-04-30
sources: 4
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
| [[admiral R Package]] | SDTM → ADaM datasets |
| [[tern R Package]] | TLG analysis functions (KM, forest, Cox) |
| [[rtables R Package]] | Hierarchical table layout engine |
| [[chevron R Package]] | Pre-built TLG catalog as S4 objects |
| [[teal R Package]] | Interactive Shiny exploration layer |
| [[cards R Package]] | CDISC ARD objects (descriptive stats) |
| [[cardx R Package]] | Extended ARDs (model-based stats) |
| `pharmaverse.raw` | Example raw datasets for testing |
| `pharmaverse.stm` | Example SDTM datasets for reference |

### Connections

- Contains: [[sdtm.oak R Package]], [[admiral R Package]], [[tern R Package]], [[rtables R Package]], [[chevron R Package]], [[teal R Package]], [[cards R Package]], [[cardx R Package]]
- Related concept: [[CDISC SDTM]], [[CDISC ADaM]], [[Analysis Results Data]]
- Output format: [[Dataset-JSON]] (R Consortium Pilot 5 demonstrated Pharmaverse packages producing Dataset-JSON)
- Validation context: [[R Validation Hub]] and [[riskmetric R Package]] assess Pharmaverse package quality
- Sources: [[SDTM programming in R using {sdtm.oak} package]], [[Explore the Pharmaverse Examples (2025)]], [[Faster Clinical Trial Reporting — Pharmaverse Beginner Guide]]
- Related topic: [[Regulatory Data Submission Standards]], [[R Package Validation in Regulated Environments]], [[TLG Production Pipeline in R]]
