---
title: "How to Write Robust shinytest2 Tests for R Shiny Apps"
type: source
tags: [shinytest2, shiny, testing, r-package, data-testid, bdd, cucumber, robust-testing]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# How to Write Robust shinytest2 Tests for R Shiny Apps

**Raw file**: `raw/sources/How to Write Robust shinytest2 Tests for R Shiny Apps.md`  
**Author(s)**: Jakub Sobolewski  
**Year**: 2025  
**Type**: blog-post  
**Venue**: jakubsobolewski.com/blog/robust-shinytest2/ (August 18, 2025)

## Summary

Argues that default shinytest2 tests are brittle because they reference raw Shiny input IDs (which change during refactoring) or take fragile full-app snapshots. Proposes a 4-step pattern: (1) attach `data-testid` attributes to UI components, (2) use `data-testtype` to encode how each component is interacted with, (3) extend `AppDriver` with a custom `ShinyDriver` R6 class that dispatches interactions via testid/testtype, (4) wrap reusable sequences in named step functions for readable, behavior-focused tests. Optionally, step functions can be formatted as Cucumber/Given-When-Then specs.

## Key Points

- **Core problem**: raw input ID references in tests couple tests to implementation, not behavior; break when UI is refactored
- **`data-testid`**: stable semantic identifier for a component; changes only when business meaning changes (use `htmltools::tagAppendAttributes()`)
- **`data-testtype`**: encodes the interaction type (e.g., `picker_input`, `action_button`); drives dispatch logic
- **Custom `ShinyDriver` R6 class**: inherits from `shinytest2::AppDriver`; `dispatch(testable_id, ...)` method looks up ID and type via JS, then delegates to the correct interaction function
- **Step functions** (`i_use_default_mapping()`, `i_set()`) make tests read as executable specifications
- Optional Cucumber (gherkin) syntax for stakeholder-readable test specs

## Methods / Concepts Covered

- [[Shiny App Testing in Pharma]] — advanced pattern for robust test design
- [[GxP Validation]] — stable, readable tests are better validation documentation

## Connections

- Related source: [[Shiny Testing Overview]]
- Tool: [[shinytest2 R Package]]
- Related topic: [[R Package Validation in Regulated Environments]], [[Shiny App Testing in Pharma]]
