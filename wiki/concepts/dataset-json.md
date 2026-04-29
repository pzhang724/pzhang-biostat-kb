---
title: "Dataset-JSON"
aliases: ["Dataset-JSON"]
type: concept
tags: [cdisc, data-standards, regulatory-submission, json, xpt, r-consortium]
created: 2026-04-29
updated: 2026-04-29
sources: 2
---

# Dataset-JSON

A CDISC standard for representing clinical tabular datasets (SDTM, ADaM) using JSON, designed as a modern, open-source-friendly alternative to the SAS XPT transport format for regulatory submissions.

## Overview

For decades, the SAS XPORT (XPT) v5 transport format has been the mandated file format for SDTM and ADaM datasets in FDA submissions. XPT was designed in the 1980s for SAS-to-SAS data transfer; its constraints (8-character variable names, 200-character string limit, ASCII-only encoding, no embedded metadata, inefficient fixed-width storage) create friction with modern open-source workflows in R and Python.

CDISC Dataset-JSON provides a JSON-based alternative. It embeds rich metadata (variable labels, data types, CDISC-specific annotations) directly in each file, supports all Unicode characters, has no variable name length restriction, enables streaming of large datasets via NDJSON, and is parseable with standard tools in any programming language without specialized SAS licenses.

The FDA evaluated JSON alternatives beginning in 2022 and determined JSON was the optimal replacement format. CDISC Dataset-JSON v1.0 was released August 2023; v1.1 was finalized in 2024. The FDA re-affirmed openness to the standard via a Federal Register notice in April 2025. The R Consortium Submissions Pilot 5 (eCTD submission Fall 2025) demonstrated a fully R-based pipeline using Dataset-JSON v1.1 in place of all XPT files.

## Formal Definition

A Dataset-JSON file contains three components:

1. **Top-level metadata**: creation datetime, Dataset-JSON version, fileOID, originator, and optional Define-XML reference
2. **Column metadata**: per-variable `itemOID`, name, label, data type (`string`, `integer`, `decimal`, `float`, `datetime`, `date`, `time`)
3. **Row data arrays**: records as arrays, with `null` representing missing values; decimal values exchanged as strings to avoid floating-point rounding

File extension: `.json` (standard) or `.ndjson` (streaming; metadata on first line, one row per subsequent line).

## Key Assumptions

- **One dataset per file**: each `.json` file represents one SDTM or ADaM domain
- **Define-XML still required**: Dataset-JSON handles dataset-level metadata but regulatory submissions still require a separate define.xml for the full study metadata model
- **Validator support lag**: Pinnacle 21 Community v4.1.0 (as of 2025) did not support Dataset-JSON v1.1 validation — a key practical hurdle for broad industry adoption

## Estimation

Not a statistical model. Dataset-JSON is a data serialization standard for transport.

## Software

| Package | Language | Key Function | Notes |
|---------|----------|--------------|-------|
| `{datasetjson}` | R | `dataset_json()`, `write_dataset_json()` | Atorus Research; supports v1.0 and v1.1; used in Pilot 5 |
| Various JSON parsers | Python / R / Julia | `json.load()`, `jsonlite::fromJSON()` | Universal compatibility is a key advantage |

## Variants / Extensions

- **NDJSON format**: Newline-delimited JSON; enables streaming of large datasets without loading entire file into memory; suitable for API-based data exchange
- **Dataset-JSON v1.0 vs v1.1**: v1.1 introduced refinements to column metadata structure and data type handling; v1.1 is the current standard

## Connections

- Replaces: SAS XPT (v5 transport format) as submission transport
- Carries: [[CDISC SDTM]] and ADaM datasets
- Regulatory home: [[FDA Study Data Technical Conformance Guide]]
- Demonstrated by: [[R Consortium Submissions Working Group]] in Pilot 5
- Implemented by: [[datasetjson R Package]]
- Related topic: [[Regulatory Data Submission Standards]]

## Common Pitfalls

- **Float precision**: floating-point variables must be cast to decimal type (as strings) to avoid rounding during JSON serialization; Pilot 5 required a wrapper function to enforce this
- **Validator gap**: as of 2025, Pinnacle 21 does not validate Dataset-JSON v1.1 — submissions must work with FDA directly to document this gap
- **Label persistence**: variable labels (not native to R's data frames) must be explicitly set before serialization; `attr(df, "label")` or equivalent required per variable

## Key References

- [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]] — comprehensive motivation, standard description, and Pilot 5 implementation
- [[FDA Study Data Technical Conformance Guide]] — regulatory mandate context
