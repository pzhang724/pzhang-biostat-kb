---
title: "pharmaR — The R Validation Hub"
type: source
tags: [r-validation, pharmar, riskmetric, regulatory, open-source, r-package]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# pharmaR — The R Validation Hub

**Raw file**: `raw/sources/pharmaR website.md`  
**Author(s)**: R Validation Hub (cross-industry consortium)  
**Year**: 2024–2026  
**Type**: organization-website  
**Venue**: https://pharmar.org

## Summary

The R Validation Hub is a cross-industry collaboration to support the adoption of R within biopharmaceutical regulatory settings. Its primary outputs are the `{riskmetric}` R package (standardized quality assessment of R packages) and the `{riskassessment}` Shiny application (a GUI for reviewing package risk scores). The hub also maintains a white paper on risk-based R package validation and is working toward a regulatory-ready R package repository.

## Key Points

- Goal: provide standardized, transparent, publicly available measures of R package quality to support regulatory adoption
- **`{riskmetric}`**: measures package quality via metrics (test coverage, available documentation, community usage, lifecycle, CRAN status, etc.)
- **`{riskassessment}`**: Shiny application for interactive package risk review and documentation
- **Repository initiative**: working toward a curated, validated-package repository (analogous to a controlled internal CRAN mirror)
- White paper: *A Risk-Based Approach for Assessing R Package Accuracy Within a Validated Infrastructure*

## Methods / Concepts Covered

- [[R Package Validation in Regulated Environments]] — organizational framework
- Risk-based validation — focus on high-impact packages receiving stricter scrutiny

## Connections

- Implements: [[GxP Validation]] principles for the R ecosystem
- Related entity: [[R Validation Hub]]
- Related entity: [[riskmetric R Package]]
- Related source: [[Emily Yates — Validating GxP-Compliant R Shiny Apps]]
- Related source: [[GSWEP4R Workshop — R Package Engineering Workflow]]
- Related topic: [[R Package Validation in Regulated Environments]]

## Questions Raised

- What metrics does `{riskmetric}` weight most heavily for high-impact clinical packages?
- How does the pharmaR repository initiative relate to Posit Package Manager's validated environments?
