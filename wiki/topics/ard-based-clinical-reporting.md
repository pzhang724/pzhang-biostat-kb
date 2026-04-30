---
title: "ARD-Based Clinical Reporting"
type: topic
tags: [ard, cards, cardx, gtsummary, cdisc, clinical-reporting, reproducibility, reusability]
created: 2026-04-30
updated: 2026-04-30
sources: 3
---

# ARD-Based Clinical Reporting

## Overview

ARD-based clinical reporting is a workflow architecture where statistical analysis results are first stored as structured, machine-readable **Analysis Result Data (ARD)** objects before being rendered into tables, figures, or reports. This two-step separation of computation from presentation enables:

- **QC**: computed ARDs can be independently validated against existing tables
- **Reuse**: the same ARD feeds multiple output formats (CSR table, regulatory submission, journal article, dashboard)
- **Medical writing automation**: `inline_text()` functions read statistics directly from ARDs into R Markdown, eliminating copy-paste errors
- **Cross-study pooling**: standardized ARD format enables meta-analysis without re-running primary analyses

## The ARD Workflow in R

```
ADaM datasets (ADSL, ADTTE, ADAE, ...)
     │
     ▼ {cards} + {cardx}
ARD objects (long-format, standardized stat rows)
     │
     ├──▶ {gtsummary}  ──▶ Table 1, regression tables, inline text
     ├──▶ custom code  ──▶ CSR-specific outputs
     └──▶ QC process   ──▶ Programmatic comparison to prior outputs
```

## Key Packages

| Package | Role |
|---------|------|
| [[cards R Package]] | Core ARD creation: descriptive stats (N, mean, SD, median, CIs) |
| [[cardx R Package]] | Extended ARDs: t-tests, MMRM, regression, Wald tests, survey stats |
| [[gtsummary R Package]] | Renders ARDs into publication-ready tables; supports gt/flextable/kableExtra |

## CDISC Analysis Results Standard

The formal CDISC Analysis Results Standard (ARS) defines the regulatory framework for storing and exchanging analysis results. `{cards}` implements this standard. Key conferences in 2024–2025 (R/Pharma, PHUSE US Connect, posit::conf) featured multiple sessions on ARD-based reporting in regulatory submissions.

## Contrast with Traditional TLG Approach

| Aspect | Traditional TLG | ARD-Based |
|--------|----------------|-----------|
| Output of analysis | Rendered table/figure (Word, RTF) | Structured data object |
| QC method | Side-by-side table comparison | Programmatic ARD comparison |
| Reuse | Re-run analysis | Read existing ARD |
| Medical writing | Copy-paste statistics | Automated inline retrieval |

## Historical Context

The conceptual foundation was articulated by Marques-Barros, Widmer, Baillie (2023) with their Analysis Results Data Model (ARDM) paper. The OMOP Common Data Model was cited as the proof-of-concept that community consensus on a data model creates lasting, reusable infrastructure. CDISC launched the ARS working group around the same time; `{cards}` emerged as the R implementation.

## Connections

- Core concept: [[Analysis Results Data]]
- Input: [[CDISC ADaM]]
- Tools: [[cards R Package]], [[cardx R Package]], [[gtsummary R Package]]
- Adjacent workflow: [[TLG Production Pipeline in R]] (tern/rtables-based)
- Sources: [[A Case-Study Driven Motivation of Analysis Results Data]], [[Analysis Results Data ({cards})]], [[Extra Analysis Results Data Utilities ({cardx})]], [[Presentation-Ready Data Summary and Analytic Result Tables ({gtsummary})]]
