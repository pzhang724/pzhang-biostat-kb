---
title: "SDTM Programming in R using {sdtm.oak} Package"
aliases: ["SDTM Programming in R using {sdtm.oak} Package", "SDTM programming in R using {sdtm.oak} package"]
type: source
tags: [sdtm, cdisc, r-package, clinical-data, pharmaverse]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# SDTM Programming in R using {sdtm.oak} Package

**Raw file**: `raw/SDTM programming in R using {sdtm.oak} package.md`
**Author(s)**: Rammprasad Ganapathy (Roche); moderated by Shaolini
**Year**: 2026
**Type**: talk
**Venue**: R in Pharma workshop (YouTube, 2026-02-08)

## Summary

A hands-on workshop introducing the `{sdtm.oak}` R package for creating CDISC SDTM datasets from raw EDC data. The presenter (Ram, principal data scientist at Roche) walks through the package's 8 core algorithms using worked examples across CM, VS, AE, and DM domains. The package is production-ready — used in 50+ studies and one regulatory filing at Roche — and is part of the [[Pharmaverse]] ecosystem.

## Key Points

- `{sdtm.oak}` is EDC-agnostic: works regardless of whether raw data comes from Medidata, Veeva, or any other vendor
- Replaces ad hoc `dplyr`/`case_when()` chains with 8 named algorithms that match SDTM programming concepts
- **OKD variables** (patient identifier, row number, dataset name) are auto-generated identifiers that link source rows to target SDTM records and handle transposition automatically
- Control terminology (CT) validation happens eagerly during programming — non-standard values produce immediate warnings, preventing Pinnacle 21 errors late in the process
- Unknown/partial dates are handled natively via `assign_datetime()` with an `unknown_values` parameter
- `condition_add()` wraps any algorithm with conditional logic, replacing post-hoc filtering

## Methods / Concepts Covered

- [[CDISC SDTM]] — foundational standard; workshop assumes familiarity with SDTM domains, variables, and control terminology
- [[sdtm.oak Programming Framework]] — all 8 core algorithms demonstrated with live code across multiple domains

## Notable Quotes or Figures

> "The idea behind sdtm.oak is: instead of writing 50 lines of case_when, you call one function and the package handles the control terminology lookup, the mapping, and the validation."

> "OKD variables are the secret sauce — they make transposition invisible to the programmer."

## Connections

- Part of [[Pharmaverse]] ecosystem (alongside `admiral`, TLG packages)
- Enables end-to-end R clinical reporting pipeline: raw EDC → SDTM (sdtm.oak) → ADaM (admiral) → TLGs
- See also: [[sdtm.oak R Package]], [[Rammprasad Ganapathy]]

## Questions Raised

- How does sdtm.oak handle multi-source domains where the same variable is collected on multiple CRFs with different formats?
- What is the planned MCP agent in v0.3, and how automated will code generation be?
- Lab domain unit standardization is explicitly unresolved — what approach do teams currently use?
