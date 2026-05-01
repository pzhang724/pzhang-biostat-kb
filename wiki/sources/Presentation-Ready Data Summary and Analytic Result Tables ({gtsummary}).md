---
title: "Presentation-Ready Data Summary and Analytic Result Tables ({gtsummary})"
type: source
tags: [gtsummary, tables, r-package, summary-statistics, regression, clinical-reporting, ard]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Presentation-Ready Data Summary and Analytic Result Tables ({gtsummary})

**Raw file**: `raw/sources/Presentation-Ready Data Summary and Analytic Result Tables.md`  
**Author(s)**: Daniel D. Sjoberg and contributors  
**Year**: ongoing (R Journal article 2021)  
**Type**: other (package documentation)  
**Venue**: danieldsjoberg.com/gtsummary

## Summary

`{gtsummary}` creates publication-ready tables for data summaries (Table 1), regression models (OR, HR with reference rows), and inline statistical reporting in R Markdown. Built on `{gt}`, `{broom}`, and `{labelled}`. Integrates with the `{cards}` ARD ecosystem for pre-calculated statistics.

## Key Points

- `tbl_summary()`: automatic Table 1 — detects continuous/categorical/dichotomous variables; computes descriptive stats; reports missingness; supports `by=` group comparisons and `add_p()` for p-values
- `tbl_regression()`: regression model summary — automatically identifies logistic/Cox regression and pre-fills OR/HR column headers; handles reference rows for categorical variables
- `tbl_merge()`: side-by-side model tables
- `inline_text()`: report statistics inline in R Markdown with zero copy-paste
- Output engines: gt, flextable (Word/RTF), kableExtra, huxtable
- Can save to .png, .html, .docx, .rtf, .tex
- ARD integration: `{gtsummary}` uses `{cards}` ARD objects as a backend

## Methods / Concepts Covered

- [[Analysis Results Data]] — gtsummary acts as a consumer/renderer of ARDs
- Cox proportional hazards, logistic regression — auto-detected in `tbl_regression()`

## Connections

- Consumes: [[cards R Package]] ARD objects
- Part of: [[ARD-Based Clinical Reporting]] workflow
- Alternative to: [[tern R Package]] + [[rtables R Package]] for non-regulatory summary tables
- Related source: [[Analysis Results Data ({cards})]]
- Related topic: [[ARD-Based Clinical Reporting]]
