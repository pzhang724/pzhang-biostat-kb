---
title: "Test Coverage for Packages ({covr})"
type: source
tags: [covr, test-coverage, r-package, testing, codecov, gxp, validation]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Test Coverage for Packages ({covr})

**Raw file**: `raw/sources/Test Coverage for Packages.md`  
**Author(s)**: Jim Hester (r-lib)  
**Year**: ongoing  
**Type**: other (package documentation)  
**Venue**: covr.r-lib.org

## Summary

`{covr}` tracks test coverage for R packages by instrumenting the package code with tracking calls, running all tests, and reporting the fraction of lines/branches exercised. Integrates with Codecov and Coveralls for CI reporting. Supports R, C, C++, and Fortran code. Provides interactive HTML report, RStudio addin, and `zero_coverage()` for identifying untested lines.

## Key Points

- Coverage measured by modifying package code at the call level (not AST patching)
- `report()` opens interactive HTML line-by-line coverage view (requires DT package)
- `zero_coverage(cov)` highlights untested lines; in RStudio opens a marker pane
- Exclusion mechanisms: `.covrignore` file (glob patterns), `function_exclusions=`, `line_exclusions=`, inline `# nocov` / `# nocov start` / `# nocov end` comments
- Cannot run during R CMD check (instrumentation may affect behavior, especially for compiled code)
- `usethis::use_github_action("test-coverage")` sets up GHA workflow

## Methods / Concepts Covered

- [[GxP Validation]] — coverage metrics document test completeness for validation dossiers
- [[R Package Validation in Regulated Environments]] — coverage alongside riskmetric for risk-based package assessment

## Connections

- Related entity: [[covr R Package]]
- Related source: [[GSWEP4R Workshop — R Package Engineering Workflow]]
- Related topic: [[R Package Validation in Regulated Environments]]
