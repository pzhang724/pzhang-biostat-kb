---
title: "GSWEP4R Workshop — R Package Engineering Workflow"
type: source
tags: [r-package, software-engineering, sdlc, validation, openstatsware, gswep4r]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# GSWEP4R Workshop — R Package Engineering Workflow

**Raw file**: `raw/sources/GSWEP4R Workshop - 3 An R Package Engineering Workflow.md`  
**Author(s)**: Daniel (openstatsware / openpharma)  
**Year**: 2023-10-15  
**Type**: workshop-slides  
**Venue**: GSWEP4R Workshop (Good Software Engineering Practice for R Packages), Montreal

## Summary

Slide deck from Module 3 of the openstatsware GSWEP4R (Good Software Engineering Practice for R Packages) workshop series. Argues against the common anti-pattern of ad-hoc R package development ("idea → code → production → bug fix → repeat") and proposes a workable validated workflow with five stages: idea, design docs, programming, quality check, and publication. Grounds the case for formal engineering in empirical data: most software costs come from maintenance, and most bugs originate in requirements/design phases — justifying upfront investment in specifications.

## Key Points

- **Anti-pattern**: the "frequently used workflow" skips design, jumps straight to coding, then enters an indefinite bug-fix loop — violating regulatory requirements and wasting effort
- **Full professional workflow**: Idea → Concept → Validation Planning → Specification (URS, FS, SDS) → Programming → Verification → Formal Validation → Release → Production → Maintenance
- **Workable workflow** (pragmatic for small teams): Idea → Design Docs → Programming → Quality Check → Publication → Production
- **Why engineer properly**: ~60–70% of software lifecycle cost is maintenance; most errors introduced in requirements/design phase (Boehm 1981); regulatory compliance requires traceability
- **Design docs**: describe purpose, scope, and requirements in prose using duty/desire language (must/shall vs should)
- Produced under [[openstatsware]] working group; part of broader GAMP 5 and GxP aligned training

## Methods / Concepts Covered

- Software Development Life Cycle (SDLC) — full and pragmatic variants
- [[GxP Validation]] — regulatory compliance motivation
- URS/FS/SDS specifications — User Requirements, Functional, Software Design specs

## Notable Quotes or Figures

> Cost distribution data from doi:10.14569/IJACSA.2020.0110375 showing maintenance dominates software lifecycle cost.
> Boehm (1981) data showing most errors originate in requirements/design phases.

## Connections

- Produced by: [[openstatsware]]
- Implements: [[GxP Validation]] principles for R package development
- Related source: [[pharmaR — The R Validation Hub]]
- Related source: [[Emily Yates — Validating GxP-Compliant R Shiny Apps]]
- Related topic: [[R Package Validation in Regulated Environments]]

## Questions Raised

- What is the minimum viable "design doc" for a utility R package used internally but not submitted to regulators?
- How does the GSWEP4R workflow map to the pharmaR white paper's risk-tiered validation approach?
