---
title: "shinytest2 R Package"
type: entity
tags: [r-package, testing, shiny, snapshot, headless-browser, gxp]
created: 2026-04-30
updated: 2026-04-30
sources: 2
---

# shinytest2 R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("shinytest2")`  
**Repo**: github.com/rstudio/shinytest2  
**Maintained by**: Posit  
**Primary use**: End-to-end snapshot-based testing of R Shiny applications

### Architecture

`shinytest2` extends the older `shinytest` package. Key class: `AppDriver` — controls a headless browser session. Tests interact with the app via `AppDriver$set_inputs()`, `$click()`, `$get_value()`, `$expect_values()`.

### Robust Testing Pattern

Raw `AppDriver` use couples tests to input IDs. Recommended pattern (Sobolewski 2025):

1. Add `data-testid` + `data-testtype` to UI components via `htmltools::tagAppendAttributes()`
2. Create custom `ShinyDriver` R6 class that inherits from `AppDriver` and dispatches via testid/testtype
3. Wrap interactions in named step functions for readable, behavior-focused specs

### GxP Use

Snapshot-based tests provide documented, reproducible evidence of application behavior — directly usable as PQ (Performance Qualification) evidence in GxP dossiers. Challenge: environment-sensitivity requires consistent CI platform configuration.

### Connections

- Related concept: [[Shiny App Testing]]
- Related sources: [[Shiny Testing Overview]], [[How to Write Robust shinytest2 Tests for R Shiny Apps]]
- Related topic: [[R Package Validation in Regulated Environments]]
