---
title: "GxP Validation in Software Development Starts from the Definition of Done (Appsilon)"
type: source
tags: [gxp, validation, definition-of-done, appsilon, software-development, scrum, pharma]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# GxP Validation in Software Development Starts from the Definition of Done (Appsilon)

**Raw file**: `raw/sources/GxP Validation in Software Development starts from the Definition of Done.md`  
**Author(s)**: Paweł Przytuła (Appsilon)  
**Year**: 2024  
**Type**: blog-post  
**Venue**: appsilon.com/post/gxp-software-validation-starts-with-definition-of-done

## Summary

Argues that the Scrum Definition of Done (DoD) is an effective, practical foundation for GxP validation in pharmaceutical software development. Each company defines validation differently (technology stack, software type, regulatory purpose all vary), but using the DoD as a shared quality standard provides concrete, checkable criteria from the start of a project. Appsilon's DoD template includes traceability, reproducibility, automated testing, CI checks, and documentation requirements that map directly onto GxP traceability, accountability, and data integrity requirements.

## Key Points

- **GxP sub-domains**: GMP, GLP, GDocP, GSEP, GVP, GDP, GDMP, GAMP, GSP, GCP
- **Three GxP documentation pillars**: Traceability (full lifecycle), Accountability (who changed what and when), Data Integrity
- **IQ/OQ/PQ**: Installation Qualification, Operational Qualification, Performance Qualification — three validation stages pharma software companies must demonstrate
- **Definition of Done checklist** (Appsilon template): PR with reviewer, automated tests (unit + integration + E2E), CI passing, docs updated, no new warnings/errors, results reproducible, data sources documented, style guide followed
- No single governing body for GxP; FDA and EMA are the primary monitoring agencies

## Methods / Concepts Covered

- [[GxP Validation]] — practical implementation via DoD framework
- [[R Package Validation in Regulated Environments]] — how software engineering practices (DoD, CI/CD) satisfy GxP requirements

## Connections

- Extends: [[GxP Validation]] concept
- Related source: [[GxP Validation in Clinical Software Development (Appsilon)]] (previously ingested)
- See also: [[GSWEP4R Workshop — R Package Engineering Workflow]], [[Shiny App Testing in Pharma]]
- Related topic: [[R Package Validation in Regulated Environments]]
