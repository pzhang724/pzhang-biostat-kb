---
title: "TLG Production Pipeline in R"
type: topic
tags: [tlg, tables, listings, graphs, tern, rtables, chevron, gtsummary, pharmaverse, clinical-trials]
created: 2026-04-30
updated: 2026-04-30
sources: 7
---

# TLG Production Pipeline in R

## Overview

The TLG (Tables, Listings, and Graphs) pipeline is the final stage of the CDISC clinical data workflow, transforming ADaM analysis datasets into the submission-ready outputs that appear in Clinical Study Reports (CSRs) and regulatory packages. In R, two parallel ecosystems serve this need:

1. **Roche/insightsengineering NEST stack**: rtables + tern + chevron + teal (production-scale, complex regulatory tables)
2. **ARD-based stack**: cards + cardx + gtsummary (simpler API, publication/academic focus, growing regulatory adoption)

## Full Pipeline

```
Raw EDC data
     │
     ▼ {sdtm.oak}
SDTM datasets
     │
     ▼ {admiral} (+ TA extensions)
ADaM datasets (ADSL, ADTTE, ADAE, ADVS, ...)
     │
     ├──▶ NEST stack ──────────────────────────────────────┐
     │    {rtables} + {tern} → {chevron} → {teal}          │
     │                                                      ├──▶ Tables
     └──▶ ARD stack ────────────────────────────────────────┤   Listings
          {cards} + {cardx} → {gtsummary}                   │   Graphs
                                                            │
                                                       Submission package
                                                       (XPT / Dataset-JSON)
```

## NEST Stack (insightsengineering)

The NEST stack is designed for regulatory-quality, complex hierarchical tables matching Roche's Global Data Standards (GDS):

| Package | Role |
|---------|------|
| [[rtables R Package]] | Layout engine: declares hierarchical table structure; cell values separate from display |
| [[tern R Package]] | Analysis functions: `analyze()` functions + visualizations (KM, forest, waterfall) |
| [[chevron R Package]] | Pre-built TLG catalog: S4 objects wrapping preprocess-main-postprocess pipeline |
| [[teal R Package]] | Interactive Shiny apps: same tern functions in an interactive exploration layer |
| [[TLG Catalog (NEST)]] | Reference catalog of 100+ standard TLGs with code, output, and teal apps |

## ARD Stack (insightsengineering / ddsjoberg)

More accessible, appropriate for academic/publication outputs and growing in regulatory adoption:

| Package | Role |
|---------|------|
| [[cards R Package]] | Descriptive statistics as structured ARD objects |
| [[cardx R Package]] | Model-based statistics (t-tests, MMRM, regression) as ARDs |
| [[gtsummary R Package]] | Renders ARDs into publication-ready tables (Table 1, regression tables) |

## Visualization Layer

Both stacks produce ggplot2-based figures. [[patchwork R Package]] enables composing multiple ggplot outputs into multi-panel figures.

## Learning Resources

- [[TLG Catalog (NEST)]]: comprehensive example catalog (stable + development versions)
- [[Pharmaverse Examples (2025)]]: end-to-end worked examples across SDTM/ADaM/TLG
- [[Faster Clinical Trial Reporting — Pharmaverse Beginner Guide]]: beginner-friendly overview of the full pipeline

## Connections

- Upstream: [[CDISC ADaM]], [[admiral R Package]]
- Tools: [[tern R Package]], [[rtables R Package]], [[chevron R Package]], [[teal R Package]], [[gtsummary R Package]], [[patchwork R Package]]
- ARD layer: [[ARD-Based Clinical Reporting]]
- Related topic: [[Regulatory Data Submission Standards]]
