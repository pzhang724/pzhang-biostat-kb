---
title: "riskmetric R Package"
aliases: ["riskmetric R Package"]
type: entity
tags: [r-package, r-validation, pharmar, regulatory, package-quality]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# riskmetric R Package

## R Package / Software

**Language**: R  
**CRAN**: https://cran.r-project.org/package=riskmetric  
**Maintained by**: R Validation Hub (pharmaR) consortium  
**Primary use**: Compute standardized quality and risk metrics for R packages, supporting risk-based validation decisions in regulated pharmaceutical environments

### Key Functions / Features

| Function | Purpose |
|----------|---------|
| `pkg_ref()` | Create a package reference (installed or CRAN) for assessment |
| `pkg_assess()` | Run all configured assessment functions against a package |
| `pkg_score()` | Aggregate assessment results into a composite risk score |
| `metric_*` functions | Individual metric assessments (test coverage, documentation, CRAN status, lifecycle, etc.) |

**Metrics assessed include**:
- Has a NEWS file
- Has unit tests (and test coverage percentage)
- Has vignettes / function documentation
- CRAN available / passing checks
- Community usage (download counts, reverse dependencies)
- Lifecycle status (active vs. deprecated)
- Version stability (time since last update, major version changes)

### When to Use

- When establishing a risk-based SOP for external R package validation in a regulated environment
- When creating a curated internal R package repository (select and document approved packages)
- When generating documented evidence of package quality for regulatory audit purposes
- Can feed into `{riskassessment}` Shiny app for interactive review and approval workflows

### Limitations

- Metrics measure **proxy indicators** of quality (test coverage ≠ correct results); additional functional testing of high-impact packages is still needed
- Does not assess statistical correctness of implemented methods — see [[CAMIS Working Group]] for cross-language method comparisons
- Biopharmaceutical-specific packages (Pharmaverse packages) may have lower CRAN download counts than general-purpose packages, inflating perceived risk on usage metrics

### Connections

- Maintained by: [[R Validation Hub]]
- Complements: [[CAMIS Working Group]] (correctness) and [[openstatsware]] (engineering quality)
- Implements: [[GxP Validation]] risk-based approach for package supply chain
- Referenced by: [[Emily Yates — Validating GxP-Compliant R Shiny Apps]] as a starting point for package risk quantification
- Related topic: [[R Package Validation in Regulated Environments]]
