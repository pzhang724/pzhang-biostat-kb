---
title: "cardx R Package"
type: entity
tags: [r-package, ard, clinical-reporting, statistics, mmrm, regression, cards]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# cardx R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("cardx")`  
**Repo**: github.com/insightsengineering/cardx  
**Maintained by**: insightsengineering (Roche-led consortium)  
**Primary use**: Extended Analysis Result Data (ARD) objects for model-based statistics

### Overview

`{cardx}` extends `{cards}` by providing ARD-formatted output for inferential and model-based statistics — tests, regressions, survival models, and more. Where `{cards}` covers descriptive statistics (N, mean, SD, percentages), `{cardx}` covers the "analytic" layer.

### Key Functions

| Function | Output |
|----------|--------|
| `ard_ttest()` | Student's / Welch's t-test results as ARD |
| `ard_wilcoxtest()` | Wilcoxon rank-sum test as ARD |
| `ard_chisqtest()` / `ard_fishertest()` | Chi-square and Fisher's exact tests |
| `ard_aov()` | One-way ANOVA as ARD |
| `ard_regression()` | General regression model output (lm, glm) as ARD |
| `ard_regression_basic()` | Simplified regression ARD for common models |
| `ard_survival_survfit()` | Kaplan-Meier survival estimates as ARD |
| `ard_survival_Cox()` | Cox proportional hazards model as ARD |
| `ard_emmeans()` | Estimated marginal means (from `{emmeans}`) as ARD |
| `ard_survey_*()` | Survey-weighted statistics as ARDs |

### MMRM Note

For MMRM (Mixed Model for Repeated Measures), `{cardx}` integrates with the `{mmrm}` package to produce ARD-formatted MMRM results. This is particularly relevant in pharma contexts where MMRM is the pre-specified primary analysis method for continuous endpoints.

### Dependency Note

`{cardx}` depends on `{cards}` and a set of optional statistical packages. When using in a validated environment, the `{renv}` lock file should capture exact versions of all statistical backends (lme4, survival, emmeans, mmrm, etc.) to ensure reproducibility.

### Connections

- Parent package: [[cards R Package]]
- Downstream consumer: [[gtsummary R Package]] (renders cardx ARDs into publication-ready tables)
- Related concept: [[Analysis Results Data]]
- Related topic: [[ARD-Based Clinical Reporting]]
- Source: [[Extra Analysis Results Data Utilities ({cardx})]]
