---
title: "rtables R Package"
type: entity
tags: [r-package, tables, clinical-trials, roche, insightsengineering, regulatory]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# rtables R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("rtables")`  
**Repo**: github.com/insightsengineering/rtables  
**Maintained by**: F. Hoffmann-La Roche / insightsengineering (Apache 2.0)  
**Primary use**: Framework for declaring and building complex hierarchical clinical trial tables

### Key Functions / Features

| Function | Purpose |
|----------|---------|
| `basic_table()` | Initialize a table layout |
| `split_cols_by()` | Split columns by grouping variable |
| `split_rows_by()` | Split rows by grouping variable |
| `analyze()` | Apply analysis function to leaf rows |
| `summarize_row_groups()` | Add group summary rows |
| `build_table()` | Materialize a layout + data into a table |

### Design Principles

- Cell values stored numerically, separate from display strings — enables programmatic access for cross-checks without rounding loss
- Multi-value cells supported natively
- Pagination in both horizontal and vertical directions
- CDISC-aware: distinguishes variable name from label
- Output: ASCII, HTML, PDF, PowerPoint (via flextable); RTF in development

### When to Use

- Any clinical trial table requiring hierarchical splits, multi-value cells, custom formatting, or pagination
- As the table engine underlying [[tern R Package]] and [[chevron R Package]]

### Connections

- Used by: [[tern R Package]], [[chevron R Package]]
- Source: [[Reporting Tables ({rtables})]]
- Related topic: [[TLG Production Pipeline in R]]
