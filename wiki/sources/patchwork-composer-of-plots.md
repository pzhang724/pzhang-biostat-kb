---
title: "The Composer of Plots ({patchwork})"
type: source
tags: [patchwork, ggplot2, visualization, r-package, plot-composition]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# The Composer of Plots ({patchwork})

**Raw file**: `raw/sources/The Composer of Plots.md`  
**Author(s)**: Thomas Lin Pedersen (thomasp85)  
**Year**: ongoing (CRAN)  
**Type**: other (package documentation)  
**Venue**: patchwork.data-imaginist.com

## Summary

`{patchwork}` extends ggplot2 to enable arbitrarily complex multi-panel figure composition using intuitive arithmetic operators: `+` for side-by-side, `/` for stacking, `|` for rows. Solves the same problem as `gridExtra::grid.arrange()` and `cowplot::plot_grid()` but with a more exploratory, scalable API.

## Key Points

- Core syntax: `p1 + p2` (side by side), `(p1 | p2) / p3` (grid with nesting), `p1 / p2` (stacked)
- Supports annotation, alignment across pages, and custom layout definitions
- Preserves ggplot object structure; combining is non-destructive

## Methods / Concepts Covered

- [[TLG Production Pipeline in R]] — useful for combining ggplot-based clinical figures

## Connections

- Related entity: [[patchwork R Package]]
- Complements: [[tern R Package]] (which uses ggplot2 for its visualizations)
- Alternative to: gridExtra, cowplot
