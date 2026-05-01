---
title: "teal Modules for Standard Clinical Outputs ({teal.modules.clinical})"
type: source
tags: [teal, shiny, clinical-outputs, r-package, tern, interactive, insightsengineering]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# teal Modules for Standard Clinical Outputs ({teal.modules.clinical})

**Raw file**: `raw/sources/teal Modules for Standard Clinical Outputs.md`  
**Author(s)**: insightsengineering  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: insightsengineering.github.io/teal.modules.clinical

## Summary

`{teal.modules.clinical}` provides ready-made teal modules for standard CDISC clinical outputs, enabling interactive Shiny exploration of ADaM data without building custom Shiny code. Modules leverage `{tern}` for their output generation.

## Key Points

- Modules cover data visualizations, statistical model fits, summary tables, and patient-level profile views
- Patient profile modules: `tm_t_pp_basic_info()`, `tm_g_pp_vitals()`, `tm_g_pp_patient_timeline()`
- Available in Shinylive (try without installation) in both stable and development versions
- Outputs visible in the Teal Gallery and [[TLG Catalog (NEST)]]
- All modules implement `{tern}` analysis functions as their computational backend

## Methods / Concepts Covered

- [[TLG Production Pipeline in R]] — interactive layer over the static TLG stack

## Connections

- Uses: [[tern R Package]]
- Part of: [[teal R Package]] ecosystem, insightsengineering NEST
- Related topic: [[TLG Production Pipeline in R]]
- See also: [[TLG Catalog (NEST)]], [[chevron R Package]]
