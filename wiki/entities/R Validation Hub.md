---
title: "R Validation Hub"
aliases: ["R Validation Hub"]
type: entity
tags: [organization, r-validation, pharmar, regulatory, open-source, r-package]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# R Validation Hub

## Organization

**Also known as**: pharmaR  
**Type**: Cross-industry collaboration  
**Website**: https://pharmar.org  
**Primary outputs**: `{riskmetric}` package, `{riskassessment}` Shiny app, white paper, regulatory repository initiative

### Purpose

The R Validation Hub supports adoption of R within biopharmaceutical regulatory settings by providing standardized, transparent, publicly available tools for assessing R package quality. The hub's approach is **risk-based**: not all packages require the same validation rigor — a package used for data visualization carries less risk than one implementing the primary efficacy analysis.

### Key Products

| Product | Description |
|---------|-------------|
| [[riskmetric R Package]] | R package computing standardized quality metrics for any CRAN package |
| `{riskassessment}` | Shiny app providing a GUI for reviewers to assess package risk using `{riskmetric}` scores |
| White paper | *A Risk-Based Approach for Assessing R Package Accuracy Within a Validated Infrastructure* |
| Repository initiative | Working toward a curated, audit-ready internal R package repository (analogous to validated CRAN mirror) |

### Regulatory Context

The FDA's Statistical Software Clarifying Statement does not mandate SAS — it requires that software be "reliable." The R Validation Hub provides the framework for pharmaceutical companies to demonstrate R's reliability to regulators: risk-tiered assessment, documented quality metrics, and a controlled package supply chain.

### Connections

- Primary tool: [[riskmetric R Package]]
- Broader validation ecosystem: [[GxP Validation]]
- Engineering partner: [[openstatsware]] (software engineering practices)
- Method comparison partner: [[CAMIS Working Group]]
- Related topic: [[R Package Validation in Regulated Environments]]
- Source: [[pharmaR — The R Validation Hub]]
