---
title: "Shiny App Testing in Pharma"
type: topic
tags: [shiny, testing, gxp, validation, shinytest2, covr, clinical-reporting, pharma]
created: 2026-04-30
updated: 2026-04-30
sources: 3
---

# Shiny App Testing in Pharma

## Overview

R Shiny applications are increasingly used in pharmaceutical settings for clinical data exploration, submission packages (R Consortium Pilot 2), and GxP-regulated reporting. Testing these apps requires a structured approach combining three test layers and appropriate tooling.

## Testing Strategy

See [[Shiny App Testing]] concept page for the full taxonomy. In pharma-specific contexts:

| Layer | Evidence Type | GxP Stage |
|-------|--------------|-----------|
| Unit tests | Individual function correctness | IQ/OQ |
| Server function tests | Reactive logic validation | OQ/PQ |
| Snapshot tests (shinytest2) | End-to-end user-facing behavior | PQ |
| Load tests (shinyloadtest) | Performance under concurrent users | PQ |

## GxP Validation Framework for Shiny

From [[Emily Yates — Validating GxP-Compliant R Shiny Apps]] (Formation Bio, R/Pharma 2024):

- **Pillar 1 — Validated Environment**: containerized, version-locked R environment with `{renv}`
- **Pillar 2 — Risk-Based Packages**: `{riskmetric}` + `{riskassessment}` for package qualification; [[covr R Package]] for coverage metrics
- **Pillar 3 — GAMP 5-Aligned SDLC**: requirements → design → development → testing (IQ/OQ/PQ) → release

## Making Tests Robust

The primary failure mode of Shiny tests is brittleness: tests break when UI is refactored even though behavior hasn't changed. The [[How to Write Robust shinytest2 Tests for R Shiny Apps]] pattern (Sobolewski 2025) addresses this via:

1. `data-testid` attributes (semantic, stable) instead of raw input IDs
2. `data-testtype` for interaction dispatch
3. Custom `ShinyDriver` R6 class
4. Step functions for behavior-focused test language

## Definition of Done as GxP Foundation

Appsilon's approach ([[GxP Validation in Software Development Starts from the Definition of Done]]) uses Scrum's DoD as a living GxP checklist:

- PR with reviewer; automated tests passing (unit + integration + E2E)
- CI checks passing (lint, tests); no new warnings/errors
- Documentation updated; results reproducible; data sources documented

## Test Coverage

[[covr R Package]] generates line-by-line coverage reports and integrates with GitHub Actions via `usethis::use_github_action("test-coverage")`. Coverage percentage enters validation dossiers as evidence of test completeness.

## Connections

- Concept: [[Shiny App Testing]], [[GxP Validation]]
- Tools: [[shinytest2 R Package]], [[covr R Package]]
- Context: [[R Package Validation in Regulated Environments]]
- Sources: [[Shiny Testing Overview]], [[How to Write Robust shinytest2 Tests for R Shiny Apps]], [[GxP Validation in Software Development Starts from the Definition of Done (Appsilon)]]
