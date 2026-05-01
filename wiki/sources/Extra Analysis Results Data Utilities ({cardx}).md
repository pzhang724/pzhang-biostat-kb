---
title: "Extra Analysis Results Data Utilities ({cardx})"
type: source
tags: [cardx, ard, r-package, statistical-tests, regression, mmrm, emmeans]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Extra Analysis Results Data Utilities ({cardx})

**Raw file**: `raw/sources/Extra Analysis Results Data Utilities.md`  
**Author(s)**: insightsengineering  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: insightsengineering.github.io/cardx

## Summary

`{cardx}` extends `{cards}` with ARD functions for statistical tests and regression models: t-tests, Wilcoxon rank-sum, ANOVA, MMRM, emmeans contrasts, Wald tests, survey statistics, and more. It uses utility functions from `{cards}` while delegating actual calculations to domain-specific packages (stats, mmrm, emmeans, car, survey). Importantly, `{cardx}` does not force a hard dependency on these packages, so users must explicitly reference them if using `{renv}` for package locking.

## Key Points

- Covers analytical ARDs beyond descriptive stats: `ard_stats_t_test()`, `ard_aod_wald_test()`, `ard_emmeans_contrast()`, etc.
- ARD output always includes the full parameterization (method, alternative hypothesis, conf.level, paired status, etc.) enabling future reproducibility and QC
- `construct_model()` helper builds model objects from raw data rather than accepting pre-built models, keeping the ARD's input-data provenance intact
- **renv caveat**: transitive dependencies (e.g., emmeans) won't be recorded by renv unless explicitly referenced; workaround: `library(emmeans)` or `invisible(emmeans::emmeans)`

## Methods / Concepts Covered

- [[Analysis Results Data]] — extended analytics layer of the ARD framework
- MMRM — `{mmrm}` integration for repeated measures
- [[Cross-Language Statistical Implementations (R, SAS, Python)]] — `{cardx}` standardizes output format, making cross-validation easier

## Connections

- Extends: [[cards R Package]]
- Related source: [[Analysis Results Data ({cards})]]
- Interoperates with: [[gtsummary R Package]]
- Related topic: [[ARD-Based Clinical Reporting]]
