---
title: "Faster Clinical Trial Reporting — Pharmaverse Beginner Guide"
type: source
tags: [pharmaverse, cdisc, sdtm, adam, tlg, r-packages, clinical-reporting, beginner]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Faster Clinical Trial Reporting — Pharmaverse Beginner Guide

**Raw file**: `raw/sources/Faster Clinical Trial Reporting A Beginner's Guide to Implementing CDISC SDTM and ADaM Standards with Open-Source R Packages.md`  
**Author(s)**: Fabian Hee  
**Year**: 2025  
**Type**: blog-post  
**Venue**: pharmaverse.github.io/blog, September 12, 2025

## Summary

Introductory blog post explaining the CDISC data pipeline (CDASH → SDTM → ADaM → TLG) and how Pharmaverse R packages map to each stage. Covers current challenges in clinical trials (ethics/transparency, cost, reproducibility), then shows how CDISC standards and open-source R tools address them. Emphasizes that SDTM represents source data while ADaM adds analysis-ready derivations.

## Key Points

- **CDASH** standardizes data collection at clinical sites (how data is gathered)
- **SDTM** restructures collected data for regulatory submission — it is the FDA's "raw data" view; no new derivations are added
- **ADaM** creates derived analysis-ready datasets from SDTM, enabling traceability
- **Pipeline**: `{sdtm.oak}` + `{sdtmchecks}` → SDTM; `{admiral}` → ADaM; `{rtables}` + `{tern}` → TLG outputs; `{teal}` → interactive dashboards
- Test datasets: `{pharmaversesdtm}` (example SDTM), `{pharmaverseadam}` (example ADaM), `{random.cdisc.data}` (synthetic CDISC data generator)

## Methods / Concepts Covered

- [[CDISC SDTM]] — structure and regulatory role explained
- [[CDISC ADaM]] — derivation layer; traceability from SDTM
- [[TLG Production Pipeline in R]] — full pipeline overview

## Connections

- Pipeline packages: [[Pharmaverse]], [[sdtm.oak R Package]], [[admiral R Package]], [[tern R Package]], [[rtables R Package]]
- Related source: [[Explore the Pharmaverse Examples (2025)]]
- Related topic: [[Regulatory Data Submission Standards]]
