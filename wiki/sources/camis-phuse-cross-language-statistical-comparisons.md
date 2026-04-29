---
title: "CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)"
type: source
tags: [camis, phuse, r, sas, python, statistical-methods, cross-language, regulatory]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)

**Raw file**: `raw/sources/CAMIS - A PHUSE DVOST Working Group.md`  
**Author(s)**: PHUSE DVOST Working Group (PHUSE, PSI, ASA, IASCT collaboration)  
**Year**: 2023–ongoing  
**Type**: living-reference-repository  
**Venue**: https://psiaims.github.io/CAMIS/

## Summary

CAMIS (Comparing Analysis Method Implementations in Software) is a PHUSE working group initiative that systematically compares implementations of statistical methods across R, SAS, and Python. Each entry documents how the method is implemented in each language, notes any numerical discrepancies in results, and explains whether differences reflect algorithmic choices or default parameter differences. The motivation is regulatory: FDA does not mandate any specific software, but discrepancies between languages during dual-programming QC reduce confidence in reliability. CAMIS demystifies these discrepancies so analysts can document and justify them.

## Key Points

- **Regulatory motivation**: FDA's Statistical Software Clarifying Statement says software must be "reliable" — unexplained discrepancies undermine this; CAMIS provides explanations
- **Format**: for each method, separate R, SAS, and Python pages plus a comparison page
- **Languages covered**: R, SAS, Python (and sometimes East for GSD)
- **Meets monthly**: 2nd Monday of each month; contact workinggroups@phuse.global to join

## Methods / Concepts Covered (partial; 60+ methods)

**Summary Statistics**: Rounding, summary stats, skewness/kurtosis

**General Linear Models**: One-sample t-test, paired t-test, two-sample t-test, ANOVA, ANCOVA, MANOVA, linear regression

**Generalized Linear Models**: Logistic regression, Poisson/negative binomial regression

**Non-Parametric**: Wilcoxon signed-rank, Mann-Whitney/Wilcoxon rank-sum, KS test, Kruskal-Wallis, Friedman, Jonckheere-Terpstra, Hodges-Lehman estimator

**Categorical Data**: Binomial test, McNemar, marginal homogeneity, Chi-square/Fisher's exact, CMH (stratified tables), CIs for proportions (single, two-independent, two-paired, stratified, Poisson exposure-adjusted)

**Correlated Data**: LMM random effects, MMRM (mixed model repeated measures), GLMM, GEE

**Multiple Imputation (MAR)**: Linear regression imputation, predictive mean matching

**Multiple Imputation (MNAR)**: Tipping point/delta adjustment, reference-based imputation/rbmi

**Correlation**: Pearson, Spearman, Kendall's rank

**Survival Models**: KM/log-rank/Cox PH, cause-specific hazards, AFT, weighted log-rank, recurrent events, CIF, tobit regression, RMST

**Bayesian Methods**: Intro (placeholder), MMRM (placeholder)

**Sample Size/Power**: Superiority, equivalence, non-inferiority (single timepoint), average bioequivalence, Cochran-Armitage trend test, group sequential designs (survival, binary)

**Causal Inference / ML**: Propensity score matching, propensity score weighting, clustering, PCA, Lasso, Ridge, XGBoost

**Other**: Survey statistics

## Connections

- Uses and compares: [[CDISC SDTM]] (clinical context for many methods)
- Organizational: [[CAMIS Working Group]]
- Related entity: [[openstatsware]] (parallel software engineering initiative)
- Related topic: [[Cross-Language Statistical Implementations (R, SAS, Python)]]

## Questions Raised

- Which methods show the largest practical numerical discrepancies between R and SAS (i.e., where does choice of language actually matter)?
- Are CAMIS comparisons routinely cited in ADRGs or statistical analysis plans to justify dual-programming differences?
