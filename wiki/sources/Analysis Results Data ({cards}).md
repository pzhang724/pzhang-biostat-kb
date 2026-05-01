---
title: "Analysis Results Data ({cards})"
type: source
tags: [ard, cards, cdisc, r-package, clinical-reporting, analysis-results]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Analysis Results Data ({cards})

**Raw file**: `raw/sources/Analysis Results Data.md`  
**Author(s)**: insightsengineering (Roche/Genentech led)  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: insightsengineering.github.io/cards

## Summary

`{cards}` (CDISC Analysis Result DataSetS) is the R implementation of the CDISC Analysis Results Standard. It creates machine-readable, tidy ARD objects containing both the statistical results and the full parameterization used to produce them. These objects feed into table generation, QC, medical writing pipelines, and cross-study analysis.

## Key Points

- Creates **CDISC-compliant Analysis Result Data (ARD)** objects — long-format data frames with columns: `group1`, `group1_level`, `variable`, `stat_name`, `stat_label`, `stat`, `context`, `fmt_fun`, `warning`, `error`
- **Use cases**: (1) QC of existing tables, (2) pre-calculate stats for table/figure pipelines, (3) medical writers access statistics inline without copy-paste, (4) cross-study re-use and meta-analysis
- `ard_summary()` is the primary function for descriptive stats (N, mean, SD, median, quartiles, min, max)
- Works directly with ADaM datasets (e.g., ADSL)
- Extended by [[cardx R Package]] for model-based statistics (t-tests, regression, etc.)

## Methods / Concepts Covered

- [[Analysis Results Data]] — the concept this package implements
- [[CDISC ADaM]] — input data format

## Connections

- Implements: [[Analysis Results Data]]
- Extended by: [[cardx R Package]]
- Used with: [[gtsummary R Package]] (downstream table rendering from ARDs)
- Related source: [[Extra Analysis Results Data Utilities ({cardx})]], [[A Case-Study Driven Motivation of Analysis Results Data]]
- Related topic: [[ARD-Based Clinical Reporting]]
