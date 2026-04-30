---
title: "ADaM in R Asset Library"
type: source
tags: [admiral, adam, cdisc, r-package, pharmaverse, clinical-trials]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# ADaM in R Asset Library

**Raw file**: `raw/sources/ADaM in R Asset Library.md`  
**Author(s)**: Pharmaverse admiral team (cross-industry)  
**Year**: ongoing (CRAN releases)  
**Type**: other (package documentation)  
**Venue**: pharmaverse.github.io/admiral

## Summary

The `{admiral}` package is the Pharmaverse's open-source R toolbox for creating CDISC ADaM datasets from SDTM data. It provides a modular, function-based approach (rather than a black-box solution) with four guiding design principles: usability, simplicity, findability, and readability. The package family includes a core package plus therapeutic area (TA) extensions (oncology, ophtha, vaccine, peds, metabolic, neuro) and company-specific plug-ins.

## Key Points

- **Design philosophy**: "opinionated" modular approach — users compose ADaM datasets by calling re-usable building-block functions, making derivations transparent and auditable
- **Release schedule**: biannual CRAN releases (Q2 and Q4/Q1); TA extensions may release less frequently or ad hoc
- **Extension family**: `{admiralonco}`, `{admiralophtha}`, `{admiralvaccine}`, `{admiralpeds}`, `{admiralmetabolic}`, `{admiralneuro}` for TA-specific algorithms
- **Design principle — Readability**: all functions follow a programming strategy; tidyverse (dplyr) preferred; nesting kept shallow
- **Scope**: cannot cover 100% of all ADaM derivations (study-specific needs always remain); not a black-box automation

## Methods / Concepts Covered

- [[CDISC ADaM]] — the standard the package implements; ADSL, BDS, OCCDS dataset types
- [[CDISC SDTM]] — input format; admiral takes SDTM as source
- [[Pharmaverse]] — admiral is the ADaM-layer cornerstone of the Pharmaverse ecosystem

## Connections

- Implements: [[CDISC ADaM]]
- Part of: [[Pharmaverse]]
- Downstream users: [[tern R Package]], [[chevron R Package]] (receive ADaM output from admiral)
- Extension of: [[sdtm.oak R Package]] (SDTM precedes ADaM in the pipeline)
- Related source: [[Faster Clinical Trial Reporting — Pharmaverse Beginner Guide]]
- Related topic: [[Regulatory Data Submission Standards]], [[TLG Production Pipeline in R]]
