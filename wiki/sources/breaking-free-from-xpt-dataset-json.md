---
title: "Breaking Free from the XPT — Dataset-JSON as Regulatory Transport"
type: source
tags: [cdisc, dataset-json, xpt, regulatory-submission, r-consortium, pharmaverse, data-standards]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# Breaking Free from the XPT — Dataset-JSON as Regulatory Transport

**Raw file**: `raw/sources/Breaking Free from the XPT Exploration of Dataset-JSON as an Alternative Transport File to Regulatory Agencies – Breaking Free from the XPT.md`  
**Author(s)**: PHUSE / R Consortium Submissions Working Group  
**Year**: 2026  
**Type**: conference-paper  
**Venue**: PHUSE US Connect 2026

## Summary

This paper argues for replacing the legacy SAS XPORT (XPT) format with CDISC Dataset-JSON v1.1 as the transport file for SDTM and ADaM datasets in FDA regulatory submissions. It documents the technical and ecosystem limitations of XPT (1980s design, 8-character variable names, ASCII-only, no embedded metadata), explains the Dataset-JSON standard, and describes R Consortium Submissions Working Group **Pilot 5** — the first publicly reproducible submission package using Dataset-JSON with R-generated ADaM datasets. Pilot 5 was submitted to the FDA via eCTD portal in Fall 2025.

## Key Points

- **XPT limitations**: 8-char variable names, 200-char string length, ASCII-only, no embedded metadata, inefficient fixed-width storage (up to 70% waste), not native to open-source tools
- **Dataset-JSON advantages**: self-contained metadata (labels, types embedded), human-readable/auditable, universal JSON parsers across languages, API-compatible, supports NDJSON streaming for large datasets
- **Standard history**: FDA evaluated JSON alternatives in 2022; CDISC Dataset-JSON v1.0 released August 2023; v1.1 finalized 2024; FDA re-affirmed the standard via Federal Register notice April 2025
- **R Submissions Pilot lineage**: Pilot 1 (TLFs in R, SAS XPT data) → Pilot 3 (ADaM rebuilt in R, still XPT) → Pilot 5 (full R pipeline, all data as Dataset-JSON v1.1)
- **Pilot 5 implementation**: uses `{datasetjson}` R package; treats QC as an artifact (`qcReport.qmd`, `tlf-qc.qmd`); LLM-assisted ADRG documentation pipeline
- **Practical challenges**: Dataset-JSON v1.1 not yet supported in Pinnacle 21 Community v4.1.0 at time of submission; float-to-decimal type handling required wrapper functions
- **Status at time of writing**: FDA requested minor re-work after initial submission; re-submitted January 2026; final review outcome pending

## Methods / Concepts Covered

- [[Dataset-JSON]] — the CDISC standard being advocated; full technical description
- [[CDISC SDTM]] — transport applies to both SDTM and ADaM datasets
- [[R Consortium Submissions Working Group]] — organizational context for the Pilots

## Notable Quotes or Figures

> "XPT is not 'bad' — as it is widely supported and deeply embedded in regulatory processes. However, when viewed through a modern software lens, it unduly burdens the acceptance of modern software practices."

> "Binary formats sacrifice these readability and auditability characteristics — considerations that matter critically in regulatory review contexts where transparency and reproducibility are paramount."

## Connections

- Technical standard: [[Dataset-JSON]]
- Regulatory context: [[FDA Study Data Technical Conformance Guide]]
- R tooling: [[datasetjson R Package]]
- Organizational: [[R Consortium Submissions Working Group]]
- Related topic: [[Regulatory Data Submission Standards]]
- Predecessor SDTM content: [[CDISC SDTM]]

## Questions Raised

- When will Pinnacle 21 support Dataset-JSON v1.1 validation, unblocking wider industry adoption?
- Will FDA's Federal Register re-affirmation translate into a hard XPT sunset deadline?
- How does Dataset-JSON interact with SEND (non-clinical) submission requirements?
