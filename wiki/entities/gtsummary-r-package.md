---
title: "gtsummary R Package"
type: entity
tags: [r-package, summary-tables, regression, ard, clinical-reporting, reproducibility]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# gtsummary R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("gtsummary")`  
**Repo**: github.com/ddsjoberg/gtsummary  
**Maintained by**: Daniel D. Sjoberg and contributors  
**Primary use**: Publication-ready summary tables and regression model tables

### Key Functions

| Function | Purpose |
|----------|---------|
| `tbl_summary()` | Table 1: descriptive statistics by group |
| `tbl_regression()` | Regression table with reference rows (logistic, Cox, etc.) |
| `tbl_merge()` | Side-by-side model tables |
| `inline_text()` | Extract statistics for R Markdown inline reporting |
| `add_p()`, `add_n()`, `bold_labels()` | Table modifiers |

### ARD Integration

`{gtsummary}` acts as a consumer and renderer of [[cards R Package]] ARD objects. This positions it in the ARD-based reporting workflow: cards/cardx produce structured results → gtsummary renders them into publication tables.

### Output Formats

Supports multiple rendering engines: `{gt}` (HTML/PDF), `{flextable}` (Word/RTF/PowerPoint), `{kableExtra}`, `{huxtable}`. Tables can be saved as PNG, HTML, docx, RTF, LaTeX.

### When to Use

- Academic or regulatory Table 1 (demographics by treatment arm)
- Regression results for manuscripts or CSRs
- Any setting where `{rtables}` is too heavy and results don't require the full rtables layout API

### Connections

- Consumes: [[cards R Package]] ARD objects
- Built on: {gt}, {broom}, {labelled}
- Source: [[Presentation-Ready Data Summary and Analytic Result Tables ({gtsummary})]]
- Related topic: [[ARD-Based Clinical Reporting]], [[TLG Production Pipeline in R]]
