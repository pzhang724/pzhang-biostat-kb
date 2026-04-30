---
title: "Introduction to Chevron ({chevron})"
type: source
tags: [chevron, tlg, r-package, tern, rtables, insightsengineering, clinical-standards]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Introduction to Chevron ({chevron})

**Raw file**: `raw/sources/Introduction to Chevron.md`  
**Author(s)**: insightsengineering  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: insightsengineering.github.io/chevron

## Summary

`{chevron}` provides a catalog of pre-built, standards-compliant TLG objects stored as S4 `chevron_tlg` virtual-class instances. Each output (e.g., `aet02` for adverse events by SOC/PT) encapsulates three functions — `preprocess`, `main`, and `postprocess` — and is invoked via `run(aet02, adam_db)`. The naming convention `<gds_template_id>_main` reflects Roche's Global Data Standards (GDS), making chevron a reference implementation of those standards.

## Key Points

- **S4 object model**: each TLG is a `chevron_t`, `chevron_l`, or `chevron_g` object with slots for `main`, `preprocess`, `postprocess`; access via methods `main(aet02)`, `preprocess(aet02)`, `postprocess(aet02)`
- `run(chevron_tlg_object, adam_db)` is the uniform execution interface; `adam_db` is always a named list of ADaM data frames
- **Preprocessing**: uses base R, dplyr, dunlin; users are expected to customize for their study data (template only)
- **Main functions**: use rtables + tern for tables; ggplot2/lattice/grid for graphs; rlistings for listings
- Custom TLG objects can be created with `chevron_t()`, `chevron_l()`, `chevron_g()` constructors

## Methods / Concepts Covered

- [[TLG Production Pipeline in R]] — chevron wraps the full preprocess-analyze-render pipeline
- [[CDISC ADaM]] — adam_db input always follows ADaM structure

## Connections

- Uses: [[tern R Package]], [[rtables R Package]]
- Part of: insightsengineering NEST stack
- Related topic: [[TLG Production Pipeline in R]]
- Related source: [[TLG Catalog (NEST)]]
