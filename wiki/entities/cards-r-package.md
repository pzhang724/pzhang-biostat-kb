---
title: "cards R Package"
type: entity
tags: [r-package, ard, cdisc, clinical-reporting, insightsengineering]
created: 2026-04-30
updated: 2026-04-30
sources: 2
---

# cards R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("cards")`  
**Repo**: github.com/insightsengineering/cards  
**Maintained by**: insightsengineering (Roche/Genentech) and contributors  
**Primary use**: Create CDISC-compliant Analysis Result Data (ARD) objects

### Key Functions

| Function | Purpose |
|----------|---------|
| `ard_summary()` | Descriptive statistics ARD (N, mean, SD, median, quartiles, min, max) |
| `ard_categorical()` | Frequency/proportion ARDs for categorical variables |
| `ard_missing()` | Missing data summary ARD |

### ARD Format

ARD objects are long-format data frames with standardized columns:
- `group1` / `group1_level`: grouping variable and level
- `variable`: analysis variable
- `stat_name` / `stat_label` / `stat`: statistic identifier, human label, value
- `context`: analysis context string
- `fmt_fun`: formatting function
- `warning` / `error`: any issues during computation

### When to Use

- Pre-computing statistics for inclusion in summary tables
- QC of existing clinical tables (recompute and compare)
- Medical writing pipelines (inline stats without copy-paste)
- Cross-study analysis and pooling (standardized result format)

### Connections

- Implements: [[Analysis Results Data]] concept
- Extended by: [[cardx R Package]] (model-based statistics)
- Used by: [[gtsummary R Package]] (rendering ARDs into publication tables)
- Related source: [[Analysis Results Data ({cards})]]
- Related topic: [[ARD-Based Clinical Reporting]]
