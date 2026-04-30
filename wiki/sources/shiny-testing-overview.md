---
title: "Shiny Testing Overview"
type: source
tags: [shiny, testing, shinytest, testthat, snapshot, r-package, gxp, validation]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Shiny Testing Overview

**Raw file**: `raw/sources/Shiny testing overview.md`  
**Author(s)**: Winston Chang (Posit)  
**Year**: ongoing  
**Type**: other (documentation article)  
**Venue**: shiny.posit.co/r/articles/improve/testing-overview/

## Summary

Comprehensive overview of the three categories of Shiny application tests: unit tests (pure R functions), server function tests (reactive expressions in a simulated session), and snapshot-based tests (headless browser, records state + screenshots). Discusses scope, creation workflow, sensitivity to change, and CI integration. Introduced with Shiny 1.5.0's `runTests()`.

## Key Points

- **Unit tests**: test functions in `R/` directory; `testthat`; fast, narrowly scoped; no browser
- **Server function tests**: `testServer()` with `session$setInputs()`; tests reactives/outputs without browser; `session$flush()` triggers reactive updates
- **Snapshot-based tests**: `recordTest()` records interactions; `viewTestDiff()` for visual diff review; captures full app state + screenshots; sensitive to OS/R/package version changes
- CI/CD: unit + server tests easy to automate; snapshot tests require consistent platform (avoid false positives from rendering differences)
- `shinyloadtest` for performance/load testing (separate from correctness)
- **GxP relevance**: snapshot tests provide documented, reproducible evidence of correct behavior — valuable for validation audit trails

## Methods / Concepts Covered

- [[Shiny App Testing in Pharma]] — foundational taxonomy of testing approaches
- [[GxP Validation]] — testing as validation evidence

## Connections

- Implements: [[Shiny App Testing in Pharma]]
- Related source: [[How to Write Robust shinytest2 Tests for R Shiny Apps]]
- See also: [[Emily Yates — Validating GxP-Compliant R Shiny Apps]], [[R Package Validation in Regulated Environments]]
- Tools: [[shinytest2 R Package]]
