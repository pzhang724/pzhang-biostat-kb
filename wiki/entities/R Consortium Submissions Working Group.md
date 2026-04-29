---
title: "R Consortium Submissions Working Group"
aliases: ["R Consortium Submissions Working Group"]
type: entity
tags: [organization, r-consortium, regulatory-submission, fda, open-source, clinical-trials]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# R Consortium Submissions Working Group

## Organization

**Type**: Working group under R Consortium  
**Focus**: Demonstrating that open-source R-based submission packages can meet FDA regulatory expectations  
**Website**: https://rconsortium.github.io/submissions-wg/  
**Mission**: Make R-based clinical trial regulatory submissions easier today (by showing working examples) and tomorrow (by influencing FDA/industry standards)

### Pilot Program

The working group has conducted a series of public, reproducible submission-like packages ("Pilots"), each building on the prior:

| Pilot | Year | Focus |
|-------|------|-------|
| Pilot 1 | 2021 | TLFs generated in R; SDTM/ADaM from SAS XPT |
| Pilot 2 | 2022–2023 | TLFs packaged into an R Shiny app |
| Pilot 3 | 2023–2024 | ADaM datasets rebuilt in R; output still XPT |
| Pilot 4 | 2023–2026 | Pilot 2 delivered as WebAssembly and container |
| Pilot 5 | 2025–2026 | Full R pipeline; all datasets as Dataset-JSON v1.1 |

Each Pilot is submitted via the FDA's eCTD portal and reviewed by actual FDA statisticians. Upon successful review, the FDA issues a "Statistical Review and Evaluation" recognition letter.

### Significance

- Provides public reference implementations that industry teams can fork and adapt
- Directly engages FDA reviewers to surface practical issues (package installation, data format, derivation questions)
- Pilot 5 (Dataset-JSON) was submitted Fall 2025 — the first public demonstration of a full Dataset-JSON submission pipeline in R

### Connections

- Key technology: [[Dataset-JSON]], [[datasetjson R Package]]
- Source: [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]]
- Related entity: [[Pharmaverse]] (packages used in the submission pipelines)
- Related entity: [[R Consortium pharma-skills — BioPharma Agent Skills]] (same R Consortium umbrella)
- Related topic: [[Regulatory Data Submission Standards]]
