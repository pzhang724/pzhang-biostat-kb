---
title: "CDISC ADaM"
type: concept
tags: [cdisc, adam, analysis-data, adsl, adtte, bds, occds, clinical-trials, regulatory]
created: 2026-04-30
updated: 2026-04-30
sources: 3
---

# CDISC ADaM

## Definition

**CDISC Analysis Data Model (ADaM)** is the CDISC standard for creating analysis-ready datasets from [[CDISC SDTM]] data. ADaM datasets are mandatory for FDA NDA/BLA/ANDA submissions and must accompany the SDTM datasets and Define-XML metadata package. ADaM defines the derivation rules, traceability requirements, and dataset structures that transform SDTM (source/tabulation view) into datasets optimized for statistical analysis.

## Core Distinction from SDTM

| Aspect | SDTM | ADaM |
|--------|------|------|
| Purpose | Tabulate and preserve collected data in standardized form | Derive analysis-ready variables; optimize for statistical analysis |
| FDA view | "Raw data" / source data layer | Analysis layer |
| Derivations | None — restructuring only | Yes — derived variables, flags, analysis windows |
| Traceability | From CRF to SDTM | From SDTM variable to ADaM derived variable |

## Dataset Types

| Type | Description | Examples |
|------|-------------|---------|
| **ADSL** | Subject-Level Analysis Dataset — one row per subject; all baseline flags and population flags | Treatment arm, age, sex, analysis flags |
| **BDS** | Basic Data Structure — one or more rows per subject per analysis variable per timepoint | ADTTE (TTE endpoints), ADVS (vital signs), ADLB (lab data) |
| **OCCDS** | Occurrence Data Structure — one or more rows per subject per occurrence of an event | ADAE (adverse events), ADCM (concomitant medications) |

## Key Requirements

- **Traceability**: every derived variable must trace back to a source SDTM variable or derivation rule; documented in ADRG (Analysis Data Reviewer's Guide)
- **Analysis flags** (`ANL01FL`, `SAFFL`, `MITTFL`): Boolean character flags selecting the analysis population and observations; must be derivable from SDTM
- **PARAMCD / PARAM**: parameter-centric BDS structure allows flexible analysis across different endpoints in a single dataset
- **Define-XML**: the metadata file that describes every variable, its derivation, and its relationship to SDTM

## Implementation in R

The [[admiral R Package]] (Pharmaverse) is the primary open-source R implementation:

```r
# Typical admiral pattern: derive analysis flags from SDTM
adsl <- adsl |>
  derive_var_saffl()  |>  # safety flag
  derive_var_ittfl()  |>  # intent-to-treat flag
  derive_var_age(ageu = "YEARS")
```

The `{admiral}` ecosystem includes TA-specific extensions (`{admiralonco}`, `{admiralophtha}`, etc.) for endpoint-specific derivations.

## Validation and Submission

- ADaM datasets submitted as SAS XPT files (current FDA standard) or Dataset-JSON v1.1 (FDA-supported as of April 2025; used in R Consortium Pilot 5)
- Pinnacle 21 Enterprise is the standard validation tool used by sponsors before submission
- ADRG documents all derivation decisions; reviewers use it to understand and reproduce analyses

## Connections

- Derived from: [[CDISC SDTM]]
- Implemented by: [[admiral R Package]]
- Consumed by: [[tern R Package]], [[chevron R Package]], [[gtsummary R Package]], [[Analysis Results Data]]
- Transport: [[Dataset-JSON]]
- Source: [[ADaM in R Asset Library]], [[Faster Clinical Trial Reporting — Pharmaverse Beginner Guide]], [[Study Data for Submission to CDER and CBER (FDA)]]
- Related topic: [[Regulatory Data Submission Standards]], [[TLG Production Pipeline in R]]
