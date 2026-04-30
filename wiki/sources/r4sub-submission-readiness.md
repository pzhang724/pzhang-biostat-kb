---
title: "r4sub — Ready for Submission"
type: source
tags: [r4sub, submission-readiness, fmea, sci, traceability, regulatory, r-package]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# r4sub — Ready for Submission

**Raw file**: `raw/sources/r4sub — Ready for Submission.md`  
**Author(s)**: R4SUB team  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: r4sub.github.io/r4sub/

## Summary

`{r4sub}` is a meta-package for the R4SUB (Ready for Submission) ecosystem — an integrated toolkit for assessing and demonstrating clinical submission readiness of ADaM/SDTM pipelines. A single `library(r4sub)` attaches: evidence scoring (r4subcore, r4subscore), FMEA-based risk quantification (r4subrisk), ADaM/SDTM traceability (r4subtrace), regulatory profiles (r4subprofile), label/Define-XML usability indicators (r4subusability), and example datasets (r4subdata). An optional Shiny dashboard (r4subui) is available separately.

## Key Points

- **Submission Confidence Index (SCI)**: composite score across pillars computed via `compute_indicator_scores()` → `compute_pillar_scores()` → `compute_sci()`
- **FMEA-based risk**: failure mode and effects analysis quantification of submission risks
- **Traceability engine**: ADaM/SDTM variable-level traceability documentation
- **Usability indicators**: label quality, Define-XML compliance, annotations assessment
- **Regulatory profiles**: pre-configured FDA/EMA submission profile checks

## Methods / Concepts Covered

- [[CDISC ADaM]], [[CDISC SDTM]] — the datasets being assessed
- [[GxP Validation]] — submission readiness as the downstream goal of GxP

## Connections

- Related entity: [[r4sub R Package]]
- Complements: [[riskmetric R Package]] (package-level risk) vs. r4sub (submission-level risk)
- Related topic: [[Regulatory Data Submission Standards]], [[R Package Validation in Regulated Environments]]
