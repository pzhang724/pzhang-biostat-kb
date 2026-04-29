---
title: "Regulatory Data Submission Standards"
type: topic
tags: [regulatory, fda, cdisc, sdtm, adam, dataset-json, xpt, submission, data-standards]
created: 2026-04-29
updated: 2026-04-29
sources: 4
---

# Regulatory Data Submission Standards

The technical standards governing how clinical trial data must be formatted, structured, and transported when submitted to regulatory agencies (FDA, EMA, PMDA) for drug approval.

## Overview

When a pharmaceutical sponsor submits a New Drug Application (NDA) or Biologics License Application (BLA), the FDA does not accept raw trial data in whatever format the sponsor prefers. A comprehensive set of technical standards defines the required data architecture, from how individual measurements must be organized into domain datasets all the way to which file format is used to transfer those datasets to the agency.

The current FDA framework is:

```
Raw EDC data
    ↓ [transformed using {sdtm.oak} or similar]
SDTM datasets (tabulation layer)
    ↓ [mapped to analysis-ready format via {admiral}]
ADaM datasets (analysis layer)
    ↓ [serialized to transport format]
XPT (historical) or Dataset-JSON v1.1 (emerging)
    ↓ [packaged with define.xml + ADRG + SDRG]
eCTD regulatory submission portal
```

The technical specifications for this entire stack are governed by the **FDA Study Data Technical Conformance Guide** (SDTCG), which references CDISC's SDTM and ADaM implementation guides as the authoritative standards for dataset structure.

## Core Concepts

- [[CDISC SDTM]] — the Study Data Tabulation Model; organizes clinical data into standardized domains (DM, AE, CM, VS, LB, etc.)
- [[Dataset-JSON]] — the emerging JSON-based transport format replacing SAS XPT v5; supported in FDA Federal Register notice (April 2025)
- ADaM — Analysis Data Model; built on top of SDTM; provides analysis-ready datasets
- define.xml — metadata companion file describing all datasets and variables; required with every submission

## The XPT→Dataset-JSON Transition

The SAS XPT (v5 transport) format has served as the submission transport since the 1980s. Its limitations — 8-character variable names, ASCII-only encoding, no embedded metadata, inefficient storage, poor fit with modern open-source tools — motivated the CDISC Dataset-JSON standard.

| Dimension | SAS XPT v5 | Dataset-JSON v1.1 |
|-----------|------------|-------------------|
| Variable name limit | 8 characters | No limit |
| String length limit | 200 characters | No limit |
| Encoding | ASCII only | Full Unicode (UTF-8) |
| Embedded metadata | None (requires define.xml) | Labels, types embedded |
| Human-readable | No (binary) | Yes (text JSON) |
| Open-source tooling | SAS-native; R via `{haven}` | Universal JSON parsers |
| Streaming large datasets | No | Yes (NDJSON format) |
| FDA status | Historical standard | Re-affirmed April 2025 |
| Pinnacle 21 support | Full | v1.1 not yet supported (as of 2025) |

## Key Organizations

| Organization | Role |
|-------------|------|
| CDISC | Defines SDTM, ADaM, Dataset-JSON standards |
| FDA CDER/CBER | Mandates standard usage; reviews submissions |
| [[R Consortium Submissions Working Group]] | Public R-based submission demonstrations (Pilots 1–5) |
| PHUSE | Applied industry work; Dataset-JSON hackathons and workshops |
| Pinnacle 21 | Validation software for SDTM/ADaM conformance checking |

## Safety Reporting in the Submission Context

Beyond data structure standards, sponsors have ongoing safety reporting obligations during the IND phase: [[IND Safety Reporting]] governs expedited adverse event reporting (7-day and 15-day reports) and aggregate data assessments under 21 CFR 312.32. The SDTM ADAE domain is the data substrate for aggregate safety analysis.

## Typical Workflow

1. Design SDTM domains from CRF/EDC data specifications (per SDTMIG)
2. Program SDTM datasets in R (`{sdtm.oak}`) or SAS
3. Run Pinnacle 21 validation; resolve all Critical and Major findings
4. Program ADaM datasets from SDTM (`{admiral}` in R)
5. Serialize to transport format: XPT via `{haven}` or Dataset-JSON via `{datasetjson}`
6. Generate define.xml (automated via `{metacore}` + `{metatools}`)
7. Write SDRG (Study Data Reviewer's Guide) and ADRG (Analysis Data Reviewer's Guide)
8. Package in eCTD structure; submit via FDA gateway

## Active Debates / Open Questions

- **XPT sunset timeline**: when will FDA set a hard date requiring Dataset-JSON (or deprecating XPT)?
- **Pinnacle 21 gap**: Pinnacle 21 not supporting Dataset-JSON v1.1 is a practical blocker for industry adoption; resolution timeline unclear
- **SEND non-clinical**: does Dataset-JSON apply to non-clinical (animal study) SEND submissions?
- **PMDA and EMA alignment**: FDA re-affirmed Dataset-JSON; whether Japan and Europe will align reduces submission complexity for global programs

## Recommended Reading Order

1. [[CDISC SDTM]] — understand the tabulation standard first
2. [[FDA Study Data Technical Conformance Guide]] — regulatory mandate and context
3. [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]] — comprehensive Dataset-JSON motivation, standard, and Pilot 5 implementation
4. [[Dataset-JSON]] — technical deep-dive on the standard

## Connections

- Data generation: [[sdtm.oak R Package]], [[Pharmaverse]]
- Transport format: [[datasetjson R Package]]
- Safety obligations: [[IND Safety Reporting]]
- R ecosystem: [[R Package Validation in Regulated Environments]]
