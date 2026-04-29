---
title: "FDA Study Data Technical Conformance Guide"
type: source
tags: [fda, regulatory, cdisc, sdtm, adam, data-standards, submission]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# FDA Study Data Technical Conformance Guide

**Raw file**: `raw/sources/Study Data Technical Conformance Guide.md`  
**Author(s)**: FDA Center for Drug Evaluation and Research (CDER) / Center for Biologics Evaluation and Research (CBER)  
**Year**: 2024  
**Type**: regulatory-guidance  
**Venue**: FDA Technical Specifications Document

## Summary

The Study Data Technical Conformance Guide (SDTCG) is the FDA's primary technical specifications document for electronic study data submissions. It describes CDISC data standards requirements (SDTM, ADaM, define.xml), file format expectations, and validation requirements for regulatory submissions under 21 CFR Parts 312 and 314. The document reflects FDA's current thinking and is updated periodically to incorporate new standards and technology.

## Key Points

- Mandates CDISC SDTM for clinical study data and ADaM for analysis datasets in NDA/BLA/IND submissions
- Specifies required file formats: historically SAS XPT (v5 transport), with Dataset-JSON now recognized as an acceptable alternative
- Requires a define.xml (metadata file) to accompany all submitted datasets
- Specifies Pinnacle 21 validation as the conformance check tool; critical and major issues must be resolved before submission
- Provides guidance on study data reviewer's guides (SDRG) and analysis data reviewer's guides (ADRG)

## Methods / Concepts Covered

- [[CDISC SDTM]] — mandated tabulation standard for clinical study data
- [[Dataset-JSON]] — emerging alternative to XPT transport format
- ADaM — Analysis Data Model, downstream of SDTM; covered implicitly

## Connections

- Implements requirements for: [[CDISC SDTM]]
- File format context: [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]]
- Validated by: Pinnacle 21 Community/Enterprise
- Related topic: [[Regulatory Data Submission Standards]]

## Questions Raised

- What is the FDA's current timeline for formally requiring Dataset-JSON v1.1 in place of XPT?
- How does the SDTCG interact with PMDA (Japan) and EMA submission requirements?
