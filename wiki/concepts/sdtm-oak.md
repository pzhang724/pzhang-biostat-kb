---
title: "sdtm.oak Programming Framework"
type: concept
tags: [sdtm, cdisc, r-package, clinical-data, pharmaverse]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# sdtm.oak Programming Framework

The `{sdtm.oak}` programming framework is a modular, algorithm-centric approach to creating [[CDISC SDTM]] datasets in R, replacing ad hoc `dplyr`/`case_when()` chains with 8 reusable named algorithms.

## Overview

Traditional SDTM programming in R involves lengthy, bespoke data manipulation code: joining raw EDC datasets, applying `case_when()` for control terminology mapping, manually pivoting long, and deriving identifier variables. This code is hard to review, validate, and reuse across studies.

`{sdtm.oak}` abstracts common SDTM programming operations into 8 algorithms, each named after the programming action it performs. The algorithms handle control terminology lookup, ISO 8601 date conversion, unknown date encoding, and transposition automatically. Code becomes declarative — a programmer states *what* mapping to apply, not *how* to execute it.

The framework was developed by [[Rammprasad Ganapathy]] at Roche and is production-ready, having been used in 50+ studies and one regulatory filing as of 2026.

## The 8 Core Algorithms

| Algorithm | Function | When to Use |
|-----------|----------|-------------|
| Assign No CT | `assign_no_ct()` | 1:1 raw→SDTM mapping, no terminology validation needed (e.g., free-text fields like CMINDICATION) |
| Assign CT | `assign_ct()` | 1:1 mapping with CDISC controlled terminology lookup and validation (e.g., units, test codes) |
| Assign DateTime | `assign_datetime()` | Convert any raw date/time format to ISO 8601; handles partial/unknown dates |
| Hardcode No CT | `hardcode_no_ct()` | Assign a fixed value not collected on the CRF, no CT validation |
| Hardcode CT | `hardcode_ct()` | Assign a fixed value with CT validation (e.g., hardcode DOMAIN = "CM") |
| Condition Add | `condition_add()` | Wrapper: apply any algorithm only to rows matching a condition |
| Calc Reference Dates | `calc_reference_dates()` | Derive DM reference dates (RFSTDTC, RFXSTDTC, etc.) as min/max across multiple CRFs |
| Generate OKD | `generate_okd()` | Create the 3 OKD identifier variables in a raw dataset |

### OKD Variables

OKD ("OK D") variables are three auto-generated identifiers added to every raw dataset before mapping:

- **`okd_id`** — patient/subject identifier
- **`okd_row`** — sequential row number within the raw dataset
- **`okd_dataset_name`** — name of the source raw dataset

These variables persist through all mapping operations, linking every target SDTM record back to its source row. Crucially, they enable **automatic transposition**: when combining multiple topic variables via `bind_rows()`, the OKD variables carry the join keys, so the programmer never manually manages the pivot.

## Standard Domain Workflow

```r
# 1. Setup
cm_raw <- read_dataset("cm_raw.csv") |> convert_blanks_to_na()
okd    <- generate_okd(cm_raw, patient_var = "PATIENT", raw_source = "CM_raw")
ct     <- read_ct("study_ct.csv")

# 2. Map topic variable
cm_trt <- cm_raw |>
  assign_no_ct(raw_var = "CMTRT", sdtm_var = "CMTRT", id_vars = okd)

# 3. Map qualifiers (pipe chaining)
cm_trt <- cm_trt |>
  assign_ct(raw_var = "CMDOSU", sdtm_var = "CMDOSU",
            ct_spec = ct, ct_codelist = "C66260", id_vars = okd) |>
  assign_datetime(raw_var = "CMSTDAT", sdtm_var = "CMSTDTC",
                  format = "d-m-y", unknown_values = c("unk", "u"))

# 4. Conditional mapping
cm_trt <- cm_trt |>
  condition_add(
    condition = CMONGO == "Yes",
    algorithm = "hardcode_ct",
    sdtm_var = "CMENT", hardcode_value = "ONGOING",
    ct_spec = ct, ct_codelist = "C66257"
  )

# 5. Combine topic variables and derive common variables
cm <- bind_rows(cm_trt, cm_other_topic) |>
  mutate(
    STUDYID = "STUDY001",
    DOMAIN  = "CM",
    USUBJID = paste(STUDYID, PATIENT, sep = "-"),
    CMSEQ   = row_number()
  )
```

## Key Assumptions

- Raw data is tabular (one row per CRF record); multi-row transposition is handled via OKD
- Control terminology files are prepared as CSV with columns: `code_list`, `code`, `collected_value`, `submission_value`, `synonyms`
- Date format strings use single-character tokens: `d` (day), `m` (month), `y` (year), `h` (hour), etc.

## Software

| Package | Language | Notes |
|---------|----------|-------|
| [[sdtm.oak R Package]] | R | Implementation of this framework |
| `admiral` | R | ADaM counterpart; downstream of SDTM |
| `pharmaverse.raw` | R | Example raw datasets for testing |

## Variants / Extensions

- **v0.3 (planned)**: MCP agent for automated code generation from SDTM specs
- **`admiral`**: Applies similar algorithm-centric philosophy to ADaM dataset creation

## Connections

- Implements: [[CDISC SDTM]]
- Part of: [[Pharmaverse]]
- Developed by: [[Rammprasad Ganapathy]]
- Contrast with: manual `dplyr` + `case_when()` SDTM programming

## Common Pitfalls

- CT values not in the CT file produce warnings and are dropped — add synonyms to the CT file rather than post-processing
- `convert_blanks_to_na()` must be called on CSV imports; blank cells are not automatically `NA`
- `condition_add()` applies the filter *before* the algorithm — conditions on derived variables won't work here
- Lab domain unit standardization is not yet handled by the package (as of v0.2); teams implement custom solutions

## Key References

- [[SDTM Programming in R using {sdtm.oak} Package]] — foundational workshop with worked examples across CM, VS, AE, DM domains
