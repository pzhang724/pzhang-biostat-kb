---
title: "CDISC SDTM"
type: concept
tags: [cdisc, sdtm, clinical-data, data-standards, regulatory]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# CDISC SDTM

The Study Data Tabulation Model (SDTM) is a CDISC data standard that defines how clinical trial data must be organized for FDA and PMDA regulatory submissions.

## Overview

SDTM provides a standardized structure for tabulating the data collected during a clinical trial. Rather than submitting raw Electronic Data Capture (EDC) data — which varies by vendor and study — sponsors transform raw data into SDTM-compliant datasets before submission. This standardization allows regulators to review data from different sponsors using consistent tools and expectations.

SDTM is organized around **domains**: thematic groupings of related data. Each domain is a dataset with a defined set of variables (columns). Common domains include:

| Domain | Content |
|--------|---------|
| DM | Demographics |
| CM | Concomitant Medications |
| AE | Adverse Events |
| VS | Vital Signs |
| LB | Laboratory Tests |
| EC | Exposure to Collected Treatments |
| EX | Exposure |

Within each domain, variables are classified by role:

- **Topic variable**: Defines the nature of the record (e.g., `CMTRT` — the medication name; `VSTEST` — the vital sign test name)
- **Qualifier variables**: Provide context for the record (dose, unit, position, laterality, result, etc.)
- **Identifier variables**: Link records to subject and study (`STUDYID`, `USUBJID`, `SEQNUM`)
- **Timing variables**: Capture when the event occurred (`CMSTDTC`, `VSDY`, etc.)

## Formal Definition

SDTM datasets follow the **SDTM Implementation Guide (SDTMIG)**, which specifies for each domain:
- Required, expected, and permissible variables
- Controlled terminology (CT) code lists for categorical variables
- Derivation rules for computed variables (e.g., study day `--DY = date - RFSTDTC + 1`)

**ISO 8601** is the required format for all date/time variables (e.g., `2024-03-15T09:30:00`). Partial/unknown dates use truncation (e.g., `2024-03` for month-only).

## Key Assumptions

- **One row per observation**: Each record captures a single observation (one medication, one vital sign measurement, one adverse event)
- **Controlled terminology compliance**: Categorical values must match CDISC CT code lists exactly; non-compliant values fail Pinnacle 21 validation
- **RFSTDTC as reference**: Study days (`--DY`) are calculated relative to the subject's reference start date (`RFSTDTC` in DM)
- **Transposition for multi-result domains**: Domains like VS and LB store one result per row (wide-to-long); raw EDC data often stores multiple results per row

## Estimation

SDTM is not an analytical model — it is a data representation standard. However, programming SDTM correctly is prerequisite to downstream [[ADaM]] dataset creation and analysis.

## Software

| Package | Language | Purpose |
|---------|----------|---------|
| [[sdtm.oak R Package]] | R | Create SDTM datasets from raw EDC |
| `admiral` | R | Create ADaM datasets from SDTM |
| Pinnacle 21 | Java | Validate SDTM compliance |

## Variants / Extensions

- **CDASH** (Common Data Standards for Healthcare) — a standard for CRF data collection; CDASH variables often map directly to SDTM variables, simplifying programming
- **SENDIG** — SDTM Implementation Guide for non-clinical (animal) studies

## Connections

- Implemented by: [[sdtm.oak R Package]]
- Part of: [[Pharmaverse]] (R ecosystem for CDISC programming)
- Downstream: ADaM datasets (analysis-ready) are built on top of SDTM
- Validated by: Pinnacle 21 Community/Enterprise

## Common Pitfalls

- **Control terminology mismatches**: Raw values like "Temp" must be mapped to the CT submission value "TEMPERATURE"; unvalidated values fail regulatory checks
- **Unknown date handling**: Raw "unk-01-2019" must become `"2019-01-UN"` in ISO 8601 partial format — naive date parsing will error
- **Transposition timing**: Deciding when to pivot long is a common source of bugs; `{sdtm.oak}` handles this automatically via OKD variables
- **SEQNUM derivation**: Sequence numbers must be unique within subject and domain; often derived last after all records are combined

## Key References

- [[SDTM Programming in R using {sdtm.oak} Package]] — workshop covering practical SDTM creation with `{sdtm.oak}`
