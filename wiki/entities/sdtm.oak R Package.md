---
title: "sdtm.oak R Package"
aliases: ["sdtm.oak R Package"]
type: entity
tags: [r-package, sdtm, cdisc, clinical-data, pharmaverse]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# sdtm.oak R Package

## R Package / Software

**Language**: R
**CRAN / repo**: https://pharmaverse.github.io/sdtm.oak/
**Maintained by**: [[Rammprasad Ganapathy]] (Roche) and [[Pharmaverse]] contributors (Roche, Pfizer, GSK, and others)
**Primary use**: Create CDISC SDTM datasets from raw EDC data using a modular, algorithm-centric framework

### Key Functions / Features

| Function | Purpose |
|----------|---------|
| `generate_okd()` | Create OKD identifier variables (patient, row, dataset name) in a raw dataset |
| `assign_no_ct()` | Map a raw variable to SDTM with no control terminology lookup |
| `assign_ct()` | Map with CDISC controlled terminology validation |
| `assign_datetime()` | Convert any date/time format to ISO 8601; handles unknown dates |
| `hardcode_no_ct()` | Assign a fixed hardcoded value (no CT) |
| `hardcode_ct()` | Assign a fixed hardcoded value with CT validation |
| `condition_add()` | Wrap any algorithm with conditional row filtering |
| `calc_reference_dates()` | Derive DM reference dates across multiple CRF sources |
| `convert_blanks_to_na()` | Convert blank cells to NA after CSV import |

### When to Use

- Converting raw EDC data (any vendor) to CDISC SDTM for regulatory submission
- Replacing lengthy `dplyr`/`case_when()` SDTM mapping code with validated, readable algorithms
- When control terminology compliance needs to be enforced at programming time (not post-hoc)
- Building reproducible, study-agnostic SDTM programming pipelines in R

### Limitations

- Lab domain unit standardization not yet built in (as of v0.2) — every organization implements custom solutions
- Trial design domains (TV, TE, TS) and some study-specific domains cannot be fully automated at the package level
- No built-in unit conversion functions (°F→°C, lb→kg) — users write one-liners or helpers
- v0.3 MCP agent for automated code generation is planned but not yet released

### Connections

- Implements: [[sdtm.oak Programming Framework]], [[CDISC SDTM]]
- Part of: [[Pharmaverse]] ecosystem
- Downstream: `admiral` package (ADaM creation from SDTM)
- Source: [[SDTM programming in R using {sdtm.oak} package]]
