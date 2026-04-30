---
title: "A Case-Study Driven Motivation of Analysis Results Data"
type: source
tags: [ard, ardm, analysis-results, cdisc, kaplan-meier, reproducibility, r-pharma]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# A Case-Study Driven Motivation of Analysis Results Data

**Raw file**: `raw/sources/A Case-Study Driven Motivation of Analysis Results Data.md`  
**Author(s)**: Joana Marques-Barros (Idorsia), Lukas Widmer (Novartis), Mark Baillie (Novartis)  
**Year**: 2023  
**Type**: talk  
**Venue**: R/Pharma Workshop Series, October 19, 2023

## Summary

This workshop introduces the concept of treating statistical analysis results as data (not just as plots or tables), and proposes the Analysis Results Data Model (ARDM) as a structured way to capture, store, and reuse those results. The presenters use a Kaplan-Meier plot case study to demonstrate building a minimal ARDM and show that two reformatted outputs can be produced without re-running any analysis. The work is distinct from but informed by the CDISC Analysis Results Standard.

## Key Points

- **Paradigm shift**: treat the *output of analysis* (estimates, CIs, model parameters) as machine-readable, tidy data — not just as rendered plots/tables
- **Motivation**: researchers having to digitize Kaplan-Meier curves from PDFs is a real consequence of treating results as visual artifacts rather than data
- **Three pillars of ARDM**: (1) standard input (CDISC SDTM/ADaM), (2) analysis standard (abstract steps: load → select → fit → tidy), (3) data model (four linked tables: study, demographic variables, analysis metadata, results)
- **Six design principles**: searchable, non-redundant, separation of concerns, reproducible, interoperable, community-driven
- **OMOP Common Data Model** cited as the gold standard proof-of-concept for what community consensus on a data model can achieve for observational research
- ARDM is separate from (though aligned with) the CDISC Analysis Results Standard hackathon; neither prescribes a mandatory standard

## Methods / Concepts Covered

- [[Analysis Results Data]] — introduced and motivated as an alternative to treating results as rendered products
- [[CDISC SDTM]] — cited as "standard input" layer of the ARDM
- [[CDISC ADaM]] — cited as the second "standard input" underpinning the ARDM
- Kaplan-Meier survival curve — used as the running example for structuring results as data

## Notable Quotes or Figures

> "We have to pivot our mindset — reframe the target of the analysis to actually be a data source that you can reuse and that you can easily access."

## Connections

- Directly motivates: [[Analysis Results Data]] concept page
- Implemented by: [[cards R Package]], [[cardx R Package]], [[gtsummary R Package]]
- See also: [[CDISC ADaM]], [[Regulatory Data Submission Standards]]

## Questions Raised

- What is the right granularity for capturing analysis metadata? (e.g., all decisions made, or only finalized parameters?)
- How does the ARDM relate to the CDISC ARD standard once it matures?
