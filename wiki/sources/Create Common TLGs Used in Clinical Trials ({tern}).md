---
title: "Create Common TLGs Used in Clinical Trials ({tern})"
type: source
tags: [tern, tlg, clinical-trials, r-package, pharmaverse, insightsengineering]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Create Common TLGs Used in Clinical Trials ({tern})

**Raw file**: `raw/sources/Create Common TLGs Used in Clinical Trials.md`  
**Author(s)**: insightsengineering (Roche/Genentech led)  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: insightsengineering.github.io/tern

## Summary

`{tern}` provides the analysis functions layer of the Roche/insightsengineering TLG stack. It covers data visualizations (KM, forest, waterfall, line, STEP, Bland-Altman plots), statistical model summaries (Cox regression, logistic regression), and a comprehensive catalog of analyze/summarize functions for clinical trial tables. Outputs integrate directly into `{teal}` Shiny modules.

## Key Points

- Visualizations: `g_km()`, `g_forest()`, `g_waterfall()`, `g_lineplot()`, `g_step()`, `g_ipp()`, `g_bland_altman()`
- Statistical summaries: `summarize_coxreg()`, `summarize_logistic()`
- Analysis/summarize function catalog at `reference/analyze_functions.html` and `reference/summarize_functions.html`
- Used by [[chevron R Package]] to produce complete pre-configured TLG outputs
- TLG Catalog (see [[TLG Catalog (NEST)]]) showcases the full range of tern-based outputs

## Methods / Concepts Covered

- [[TLG Production Pipeline in R]] — tern is the analysis/visualization layer
- Cox proportional hazards — `summarize_coxreg()`
- Kaplan-Meier — `g_km()`

## Connections

- Part of: [[Pharmaverse]], insightsengineering NEST stack
- Upstream input: [[admiral R Package]] (produces ADaM input for tern)
- Used by: [[chevron R Package]], [[teal R Package]]
- Downstream catalog: [[TLG Catalog (NEST)]]
- Related topic: [[TLG Production Pipeline in R]]
