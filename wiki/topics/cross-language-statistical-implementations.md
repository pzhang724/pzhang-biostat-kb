---
title: "Cross-Language Statistical Implementations (R, SAS, Python)"
type: topic
tags: [r, sas, python, statistical-methods, camis, cross-language, regulatory, dual-programming]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# Cross-Language Statistical Implementations (R, SAS, Python)

How the same statistical methods yield different numerical results across R, SAS, and Python — and why understanding these discrepancies matters for regulatory pharmaceutical submissions.

## Overview

Dual programming (independent implementation of the same analysis in two different languages or by two different programmers) is a cornerstone of QC in regulated pharmaceutical statistics. In the SAS-centric world, both programmer and checker used SAS — discrepancies were implementation errors, not software differences. As R and Python enter the regulated space alongside SAS, a new phenomenon emerges: numerically different results that are neither errors nor disagreements, but rather reflect different algorithmic defaults, different numerical implementations, or different handling of edge cases in each language's statistical libraries.

The [[CAMIS Working Group]] (Comparing Analysis Method Implementations in Software) exists specifically to document, explain, and demystify these cross-language differences. FDA's Statistical Software Clarifying Statement says software must be "reliable" — not that results must match. CAMIS enables analysts to explain discrepancies, restoring regulatory confidence rather than treating all differences as errors.

Understanding where languages agree and disagree has practical implications:
- **Analysis plan pre-specification**: knowing that R and SAS differ in MMRM default covariance estimation allows teams to pre-specify exact model settings to ensure cross-language reproducibility
- **ADRG documentation**: ADRGs should acknowledge and explain cross-language differences for any method where CAMIS documents known discrepancies
- **Primary analysis choice**: for methods with large cross-language differences (certain non-parametric tests, survival analyses), the choice of primary analysis language should be deliberate

## Core Concepts

- [[CAMIS Working Group]] — the definitive cross-language reference
- [[Group Sequential Design]] — notable cross-language comparison (R `{gsDesign}` / `{rpact}` vs SAS `PROC SEQDESIGN` vs East)
- MMRM — mixed model repeated measures; known R/SAS differences in default covariance estimation (REML algorithm, degrees of freedom method)

## Method Comparison Landscape

The CAMIS repository covers 60+ methods. Key areas of known cross-language discrepancy:

| Method Area | Known Issues |
|------------|-------------|
| Rounding | R uses "round half to even" (banker's rounding); SAS rounds half-up; affects table formatting |
| Survival (KM) | Minor differences in tied event handling, confidence interval type defaults |
| MMRM | REML convergence criteria, degrees of freedom method (Satterthwaite vs Kenward-Roger) differ by default |
| Non-parametric tests | Continuity correction defaults, exact vs asymptotic p-value choices |
| Logistic regression | Convergence criteria, separation handling |
| Sample size (GSD) | O'Brien-Fleming/Pocock boundary computation can differ by decimal places |
| Propensity score matching | Matching algorithm defaults (greedy vs optimal) differ by package |

## Regulatory Context

The FDA's clarifying statement ("FDA does not require any specific software") is frequently cited but carries an implicit obligation: discrepancies between languages must be explained and justified, not ignored. The practical workflow is:

1. Identify methods used in the analysis
2. Check CAMIS for documented R/SAS/Python discrepancies for those methods
3. Pre-specify in the SAP which defaults will be used (convergence criteria, CI type, etc.)
4. Document in the ADRG any residual discrepancies and their source
5. Escalate only genuine unexplained differences for investigation

## Key Methods Reference (CAMIS coverage)

See [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]] for the full table. Highlights:

**Survival**: KM/log-rank/Cox PH, AFT, weighted log-rank, cause-specific hazards, RMST, CIF, recurrent events  
**Repeated measures**: MMRM, LMM random effects, GLMM, GEE  
**Missing data**: Multiple imputation (linear regression, PMM, tipping point, rbmi)  
**Clinical design**: Group sequential designs (survival, binary) — including East vs R vs SAS comparison  
**Causal inference**: Propensity score matching and weighting

## Active Debates / Open Questions

- **MMRM primary analyses**: which language's MMRM output should be primary when using R and SAS produce different estimates? Pre-specifying the exact algorithm eliminates ambiguity.
- **Python in submissions**: CAMIS now includes Python comparisons for many methods; FDA's openness to Python-based submissions lags behind R
- **LLM-generated analysis code**: when Claude or similar generates the analysis script, is there an implicit language choice? Who validates cross-language equivalence?

## Recommended Reading Order

1. [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]] — the primary reference; browse by method
2. [[Group Sequential Design]] — a well-documented area of cross-language complexity
3. [[R Package Validation in Regulated Environments]] — the broader validation context

## Connections

- Primary reference: [[CAMIS Working Group]]
- Validation context: [[R Package Validation in Regulated Environments]]
- Engineering practices: [[openstatsware]], [[GSWEP4R Workshop — R Package Engineering Workflow]]
- Submission context: [[Regulatory Data Submission Standards]]
