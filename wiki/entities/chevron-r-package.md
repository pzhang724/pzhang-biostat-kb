---
title: "chevron R Package"
type: entity
tags: [r-package, tlg, clinical-standards, insightsengineering, roche, gds, s4]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# chevron R Package

## R Package

**Language**: R  
**CRAN**: available (insightsengineering)  
**Repo**: github.com/insightsengineering/chevron  
**Maintained by**: insightsengineering  
**Primary use**: Pre-built, standards-compliant TLG catalog as S4 objects

### Architecture

Each standard output is a `chevron_tlg` S4 object with three slots:

| Slot | Access method | Content |
|------|---------------|---------|
| `main` | `main(aet02)` | TLG function (uses tern + rtables) |
| `preprocess` | `preprocess(aet02)` | Data preparation function |
| `postprocess` | `postprocess(aet02)` | Output adjustment (null report, sorting) |

### Usage

```r
run(aet02, adam_db)   # adam_db is a named list of ADaM data frames
```

Naming convention: `<gds_template_id>_main` reflects Roche's Global Data Standards (e.g., `dmt01`, `aet02`).

### When to Use

- Producing Roche GDS-aligned standard outputs directly from ADaM
- Starting point for customization: retrieve and modify the preprocess function for study-specific data
- Creating new chevron objects via `chevron_t()` / `chevron_l()` / `chevron_g()` constructors

### Connections

- Uses: [[tern R Package]], [[rtables R Package]]
- Upstream: [[admiral R Package]] (ADaM input)
- Source: [[Introduction to Chevron ({chevron})]]
- Related topic: [[TLG Production Pipeline in R]]
- Catalog: [[TLG Catalog (NEST)]]
