---
title: "Reporting Tables ({rtables})"
type: source
tags: [rtables, clinical-tables, r-package, roche, insightsengineering, regulatory]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Reporting Tables ({rtables})

**Raw file**: `raw/sources/Reporting Tables.md`  
**Author(s)**: F. Hoffmann-La Roche (insightsengineering)  
**Year**: ongoing (CRAN; Apache 2.0)  
**Type**: other (package documentation)  
**Venue**: insightsengineering.github.io/rtables

## Summary

`{rtables}` is Roche's open-source R framework for building complex, hierarchical multi-level clinical trial tables. Tables are constructed using a layout pipeline (pipe-based API: `basic_table() %>% split_cols_by() %>% analyze()`), then materialized with `build_table()`. Cell values and their display are separated — values remain numeric and accessible for programmatic cross-checking even after formatting.

## Key Points

- **Key design requirement**: cell values stored separately from display strings — critical for downstream cross-checks and value extraction
- Supports multi-value cells, column-spanning headers, pagination (horizontal and vertical), footnotes, titles
- Output formats: ASCII, HTML, PDF, PowerPoint (via flextable conversion); RTF in development
- Distinguishes name vs. label for CDISC compatibility
- Layout API: `split_cols_by()`, `split_rows_by()`, `analyze()`, `summarize_row_groups()`
- Used extensively by [[tern R Package]] and [[chevron R Package]] for actual table rendering

## Methods / Concepts Covered

- [[TLG Production Pipeline in R]] — rtables is the table-rendering engine
- [[CDISC SDTM]] / [[CDISC ADaM]] — rtables is CDISC-aware (name/label distinction)

## Connections

- Used by: [[tern R Package]], [[chevron R Package]]
- Related entity: [[rtables R Package]]
- Related topic: [[TLG Production Pipeline in R]]
