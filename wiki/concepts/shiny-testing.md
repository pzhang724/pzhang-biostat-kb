---
title: "Shiny App Testing"
type: concept
tags: [shiny, testing, shinytest2, testthat, unit-tests, snapshot, gxp, validation, r]
created: 2026-04-30
updated: 2026-04-30
sources: 3
---

# Shiny App Testing

## Overview

Testing R Shiny applications requires a three-tier strategy that matches test type to scope and purpose. Shiny 1.5.0 formalized this with `runTests()`, which dispatches across all three categories in a single call.

## Three Categories of Shiny Tests

| Category | Scope | Tool | Speed | GxP Use |
|----------|-------|------|-------|---------|
| **Unit tests** | Individual R functions in `R/` | `testthat` | Fast | Function-level correctness; easiest to maintain |
| **Server function tests** | Reactive expressions and outputs within server/module | `testServer()` + `testthat` | Medium | Validates reactive logic without browser overhead |
| **Snapshot-based tests** | Full app state + screenshots via headless browser | `shinytest`/`shinytest2` | Slow | Highest evidence for GxP validation but most brittle |

## Unit Tests

Test functions defined outside the server function. Most straightforward to write and least sensitive to unrelated changes. Rely entirely on `testthat` expectations.

```r
test_that("Lexical sorting works", {
  expect_equal(lexical_sort(c(1, 2, 3, 13)), c(1, 13, 2, 3))
})
```

## Server Function Tests

`testServer()` executes the server function in a simulated Shiny session. Inputs must be set explicitly (no UI available); reactive flush happens after `session$setInputs()`.

```r
testServer(expr = {
  session$setInputs(size = 6)
  expect_equal(output$sequence, "1 2 3 4 5 6")
})
```

## Snapshot-Based Tests (shinytest2)

`recordTest()` captures a test script + baseline snapshots. Future runs compare new snapshots to baseline; `viewTestDiff()` provides graphical diff review. Very sensitive to software environment changes — OS, R version, package versions can all trigger false failures.

**Robust shinytest2 pattern** (Sobolewski 2025 — see [[How to Write Robust shinytest2 Tests for R Shiny Apps]]):

1. Attach `data-testid` (not input IDs) to UI components via `htmltools::tagAppendAttributes()`
2. Add `data-testtype` to encode interaction type
3. Extend `AppDriver` with custom `ShinyDriver` R6 class that dispatches by testid/testtype
4. Wrap sequences in named step functions for readable, behavior-focused tests

```r
# Behavior-focused test (not wiring-focused)
test_that("plot updates by color variable", {
  driver <- ShinyDriver$new()
  i_use_default_mapping(driver)
  i_set("plot_color_variable", to = "AGE", driver)
  # verify outcome
})
```

## Test Coverage

`{covr}` measures the proportion of package lines exercised by tests. Integrates with Codecov/Coveralls for CI reporting. `zero_coverage()` highlights untested lines for remediation.

## GxP Relevance

In regulated environments (GxP Shiny apps), all three test types contribute to the validation dossier:
- Unit tests → IQ/OQ evidence that individual functions behave correctly
- Server tests → functional correctness of reactive logic
- Snapshot tests → documented, reproducible PQ evidence of user-facing behavior
- Coverage → quantified test completeness metric

## CI/CD Integration

- Unit + server tests: easy to automate on any platform (GitHub Actions, GitLab CI)
- Snapshot tests: platform-sensitive; multi-platform matrix testing reduces false positives
- GHA template: `usethis::use_github_action("test-coverage")` sets up covr reporting

## Connections

- Tools: [[shinytest2 R Package]], [[covr R Package]]
- GxP context: [[GxP Validation]], [[R Package Validation in Regulated Environments]]
- Sources: [[Shiny Testing Overview]], [[How to Write Robust shinytest2 Tests for R Shiny Apps]], [[Test Coverage for Packages ({covr})]]
- Related topic: [[R Package Validation in Regulated Environments]]
