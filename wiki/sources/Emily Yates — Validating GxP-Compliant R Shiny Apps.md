---
title: "Emily Yates — Validating GxP-Compliant R Shiny Apps"
aliases: ["Emily Yates — Validating GxP-Compliant R Shiny Apps"]
type: source
tags: [gxp, r-shiny, validation, sdlc, gamp, pharmaverse, r-in-pharma]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# Emily Yates — Validating GxP-Compliant R Shiny Apps

**Raw file**: `raw/sources/Emily Yates - Code that Cures Validating GxP-Compliant R Shiny Apps for Clinical Decisions.md`  
**Author(s)**: Emily Yates (Formation Bio)  
**Year**: 2024  
**Type**: talk (conference presentation + transcript)  
**Venue**: R/Pharma Conference 2024

## Summary

A 12-minute practical talk on building a validation framework for GxP-relevant R Shiny applications used in clinical decision-making. Yates argues that Shiny apps supporting clinical decisions (dose calculators, safety signal detection, data quality monitoring) require a fundamentally different validation approach than static R scripts. She identifies three foundational pillars: a validated Posit infrastructure, a risk-based package evaluation framework, and a GAMP 5-aligned SDLC. Presented by the Associate Director of Clinical Data Analytics at Formation Bio.

## Key Points

- **Why validation matters for Shiny apps**: patient safety (clinical decisions from the app), regulatory compliance (21 CFR Part 11, ICH E9), and business opportunity (validated framework enables faster innovation)
- **Pillar 1 — Validated environment**: validate Posit Workbench/Connect installation and configuration; establish access control, version control, directory structures; vendors available to support this
- **Pillar 2 — Risk-based package framework**: assess quality and risk of external open-source packages; create an SOP; consider `{riskmetric}` for quantification; Atorus OpenVal for pre-validated documentation
- **Pillar 3 — SDLC for Shiny apps**: a documented lifecycle governing design, build, testing, and release; must accommodate Shiny's dynamic UI complexity (not just a static script)
- **GAMP 5 alignment**: R Shiny apps likely fall under **Category 5** (custom-developed software) — the most complex and strictly regulated category; GAMP's risk-based approach maps well to SDLC documentation requirements
- **Testing approach**: automated (`{testthat}` for unit, `{shinytest2}` for app-level) + manual testing + UAT with stakeholders
- **Key lesson**: cross-functional ownership — analytics team owns SOPs but requires IT + QA partnership; internal IT education about Posit often necessary

## Methods / Concepts Covered

- [[GxP Validation]] — three-pillar framework for Shiny app validation
- GAMP 5 — risk-based software category classification; Category 5 for custom Shiny apps
- SDLC — software development lifecycle as regulatory compliance backbone

## Notable Quotes or Figures

> "Validation isn't merely a QA measure — it's a fundamental requirement for ensuring patient safety and maintaining the integrity around these really critical clinical decisions."

> "By writing our code we're actually developing software and can follow some of the same best practices as software developers in industry."

## Connections

- Implements: [[GxP Validation]] principles
- Uses: [[riskmetric R Package]] (cited as useful for package risk quantification)
- Related source: [[GxP Validation in Clinical Software Development (Appsilon)]]
- Related source: [[pharmaR — The R Validation Hub]]
- Related source: [[GSWEP4R Workshop — R Package Engineering Workflow]]
- Related topic: [[R Package Validation in Regulated Environments]]

## Questions Raised

- What distinguishes "GxP-relevant" Shiny apps (requiring full validation) from exploratory/analytical Shiny dashboards (reduced requirements)?
- How does UAT documentation satisfy FDA inspection requirements for electronic records under 21 CFR Part 11?
