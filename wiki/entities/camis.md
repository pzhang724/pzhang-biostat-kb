---
title: "CAMIS Working Group"
type: entity
tags: [organization, phuse, psi, asa, statistical-methods, cross-language, r, sas, python]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# CAMIS Working Group

## Organization

**Full name**: Comparing Analysis Method Implementations in Software  
**Type**: Cross-industry working group  
**Sponsors**: PHUSE DVOST, PSI, ASA, IASCT  
**Website**: https://psiaims.github.io/CAMIS/  
**Meeting cadence**: Monthly, 2nd Monday; contact workinggroups@phuse.global

### Purpose

CAMIS systematically documents and explains numerical differences in statistical method outputs across R, SAS, and Python. Its core insight is that discrepancies between programming languages are not errors — they often reflect different algorithmic defaults, numerical implementations, or calculation conventions, all of which can be "correct" in their own context. Understanding the source of these discrepancies is critical for regulatory submissions where dual-programming (one language for primary analysis, one for QC) is standard practice.

### Coverage

The CAMIS repository covers 60+ methods across categories:

| Category | Examples |
|----------|---------|
| Summary statistics | Rounding, summary stats, skewness/kurtosis |
| General linear models | t-tests, ANOVA, ANCOVA, MANOVA, linear regression |
| Generalized linear models | Logistic, Poisson, negative binomial regression |
| Non-parametric | Wilcoxon, Kruskal-Wallis, Friedman, Jonckheere-Terpstra |
| Categorical | Chi-square, Fisher's, CMH, binomial CIs, McNemar |
| Correlated data | LMM, MMRM, GLMM, GEE |
| Multiple imputation (MAR/MNAR) | Linear regression, PMM, tipping point, rbmi |
| Survival | KM, log-rank, Cox PH, AFT, weighted log-rank, RMST, CIF |
| Bayesian | Placeholder (in development) |
| Sample size / power | Superiority, NI, equivalence, GSD, bioequivalence |
| Causal / ML | Propensity score matching/weighting, PCA, XGBoost |
| Other | Survey statistics |

### Regulatory Context

FDA's Statistical Software Clarifying Statement affirms that it does not require a specific language — only that software be "reliable." CAMIS enables analysts to document and justify discrepancies, restoring confidence in cross-language validation and supporting the FDA's openness to R and Python alongside SAS.

### Connections

- Parallel initiative: [[openstatsware]] (software engineering practices)
- Related entity: [[R Validation Hub]] (validation infrastructure)
- Related source: [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]]
- Related topic: [[Cross-Language Statistical Implementations (R, SAS, Python)]]
- Covers: [[Group Sequential Design]], [[CDISC SDTM]] (downstream methods)
