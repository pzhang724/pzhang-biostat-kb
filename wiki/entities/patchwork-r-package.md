---
title: "patchwork R Package"
type: entity
tags: [r-package, ggplot2, visualization, plot-composition, figures]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# patchwork R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("patchwork")`  
**Repo**: github.com/thomasp85/patchwork  
**Maintained by**: Thomas Lin Pedersen  
**Primary use**: Composing multiple ggplot2 plots into a single figure layout

### Key Functions / Features

| Operator/Function | Purpose |
|------------------|---------|
| `p1 + p2` | Place plots side by side |
| `p1 / p2` | Stack plots vertically |
| `(p1 \| p2) / p3` | Grid with nesting |
| `plot_layout()` | Custom layout control |
| `plot_annotation()` | Add figure titles, tags |

### When to Use

- Combining ggplot2-based clinical figures into multi-panel displays (e.g., KM + forest plot side by side)
- Any ggplot2 composition need; superior API to gridExtra and cowplot for complex layouts

### Connections

- Complements: [[tern R Package]] (tern graphs are ggplot2 objects; patchwork can combine them)
- Source: [[The Composer of Plots ({patchwork})]]
