---
title: "teal R Package"
type: entity
tags: [r-package, shiny, interactive, clinical-data, insightsengineering, exploratory-analysis]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# teal R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("teal")`, `install.packages("teal.modules.clinical")`  
**Repo**: github.com/insightsengineering/teal  
**Maintained by**: insightsengineering  
**Primary use**: Framework for building modular, interactive Shiny applications for clinical data exploration

### Ecosystem

| Package | Role |
|---------|------|
| `{teal}` | Core framework: module registration, data connectors, UI scaffolding |
| `{teal.modules.clinical}` | Pre-built modules for standard CDISC outputs (uses tern) |
| `{teal.modules.general}` | General-purpose exploration modules |
| `{teal.data}` | Data connectors and ADaM data management |

### Key Features

- Modular architecture: each analysis tab is an independent `{teal}` module
- All modules in `{teal.modules.clinical}` are implemented using [[tern R Package]] analysis functions
- Patient-level profile modules: vitals timeline, basic info, patient events
- Available as Shinylive for zero-installation demos
- Outputs overlap with [[TLG Catalog (NEST)]] — same tern outputs, interactive versions

### When to Use

- Interactive data review during clinical trial conduct or submission review
- Building GxP-validated Shiny apps for clinical data exploration with validated `{tern}` backends
- Providing interactive complements to static TLG outputs

### Connections

- Uses: [[tern R Package]], [[rtables R Package]]
- Related: [[Shiny App Testing]] (teal apps need GxP testing)
- Related source: [[teal Modules for Standard Clinical Outputs ({teal.modules.clinical})]]
- Related topic: [[TLG Production Pipeline in R]], [[R Package Validation in Regulated Environments]]
