---
title: "TLG Catalog (NEST)"
type: source
tags: [tlg-catalog, tern, rtables, clinical-outputs, reference, quarto, insightsengineering]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# TLG Catalog (NEST)

**Raw file**: `raw/sources/TLG Catalog.md`  
**Author(s)**: insightsengineering  
**Year**: ongoing  
**Type**: other (living reference site)  
**Venue**: insightsengineering.github.io/tlg-catalog

## Summary

The TLG Catalog is the comprehensive reference collection of clinical trial Tables, Listings, and Graphs built using the NEST stack (tern + rtables). Each entry is a Quarto article with example code, synthetic data setup, output display, an interactive teal application, and reproducibility information (session info + lock file download).

## Key Points

- Every TLG is a standalone reproducible article with copyable source code
- Two rendering profiles: "Stable" (latest CRAN releases) and "Development" (latest GitHub versions)
- CI/CD: rebuilt daily and on every push; quality checked with lintr, styler, spelling; regression tested with testthat snapshots
- Provides the full index at `tlg-index.html`

## Methods / Concepts Covered

- [[TLG Production Pipeline in R]] — the catalog demonstrates the full range of what the NEST stack can produce

## Connections

- Built with: [[tern R Package]], [[rtables R Package]], [[chevron R Package]]
- Interactive version uses: [[teal R Package]]
- Related topic: [[TLG Production Pipeline in R]]
- Related source: [[Create Common TLGs Used in Clinical Trials ({tern})]]
