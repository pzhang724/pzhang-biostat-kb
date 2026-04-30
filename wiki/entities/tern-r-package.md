---
title: "tern R Package"
type: entity
tags: [r-package, tlg, clinical-trials, insightsengineering, pharmaverse, tables, graphs]
created: 2026-04-30
updated: 2026-04-30
sources: 2
---

# tern R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("tern")`  
**Repo**: github.com/insightsengineering/tern  
**Maintained by**: insightsengineering (Roche/Genentech) and contributors  
**Primary use**: Analysis functions for clinical trial tables, listings, and graphs

### Key Functions / Features

| Category | Functions |
|----------|-----------|
| Visualizations | `g_km()`, `g_forest()`, `g_waterfall()`, `g_lineplot()`, `g_step()`, `g_ipp()`, `g_bland_altman()` |
| Model summaries | `summarize_coxreg()`, `summarize_logistic()` |
| Table analyses | `analyze_*()` and `summarize_*()` families (extensive catalog) |

### Architecture

`{tern}` functions build on `{rtables}` for table structure and ggplot2/lattice for visualizations. Functions typically receive processed ADaM data and return `TableTree` objects (for tables) or ggplot objects (for graphs). These feed into `{chevron}` for pre-packaged standards and `{teal.modules.clinical}` for interactive Shiny use.

### When to Use

- Building any standard clinical trial output: demographics table (Table 1), AE table, KM plot, forest plot
- Within `{chevron}` via the `main()` slot of a `chevron_tlg` object
- Within a `{teal}` application via `teal.modules.clinical`

### Connections

- Uses: [[rtables R Package]] (table engine)
- Part of: insightsengineering NEST stack; [[Pharmaverse]]
- Upstream: [[admiral R Package]] (ADaM input)
- Used by: [[chevron R Package]], [[teal R Package]]
- Catalog: [[TLG Catalog (NEST)]]
- Source: [[Create Common TLGs Used in Clinical Trials ({tern})]]
- Related topic: [[TLG Production Pipeline in R]]
