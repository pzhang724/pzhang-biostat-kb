---
title: "covr R Package"
type: entity
tags: [r-package, test-coverage, testing, gxp, validation, ci-cd]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# covr R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("covr")`  
**Repo**: github.com/r-lib/covr  
**Maintained by**: Jim Hester (r-lib)  
**Primary use**: Measuring and reporting test coverage for R packages

### Key Functions

| Function | Purpose |
|----------|---------|
| `report()` | Interactive HTML line-by-line coverage view |
| `package_coverage()` | Compute coverage object for a package |
| `zero_coverage(cov)` | Show/highlight untested lines |
| `codecov()` | Upload results to Codecov |
| `coveralls()` | Upload results to Coveralls |

### Exclusion Mechanisms

- `.covrignore` file (glob patterns)
- `function_exclusions` argument
- `# nocov` inline comment (single line) or `# nocov start` / `# nocov end` (block)

### GxP Use

Coverage percentage documents test completeness for validation dossiers. Combined with [[riskmetric R Package]] for risk-based package assessment: low-coverage + high-risk-score = high-priority validation target.

### Connections

- Related concept: [[Shiny App Testing]], [[GxP Validation]]
- Related source: [[Test Coverage for Packages ({covr})]]
- Used alongside: [[GSWEP4R Workshop — R Package Engineering Workflow]]
- Related topic: [[R Package Validation in Regulated Environments]]
