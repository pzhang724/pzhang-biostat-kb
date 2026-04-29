---
title: "datasetjson R Package"
type: entity
tags: [r-package, cdisc, dataset-json, regulatory-submission, r-consortium, atorus]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# datasetjson R Package

## R Package / Software

**Language**: R  
**CRAN**: https://cran.r-project.org/package=datasetjson  
**GitHub**: https://github.com/atorus-research/datasetjson  
**Maintained by**: Atorus Research  
**Primary use**: Create, read, and write CDISC Dataset-JSON files from R data frames; used as the primary R toolchain for Dataset-JSON production in R Consortium Submissions Pilot 5

### Key Functions / Features

| Function | Purpose |
|----------|---------|
| `dataset_json()` | Create a Dataset-JSON object from an R data frame with column metadata |
| `write_dataset_json()` | Serialize a Dataset-JSON object to a `.json` file |
| `read_dataset_json()` | Read a Dataset-JSON file back into R |
| XPT conversion utility | Convert existing SAS XPT files to Dataset-JSON format |

**Supported standard**: Dataset-JSON v1.0 and v1.1

### When to Use

- When creating SDTM or ADaM datasets for regulatory submission and targeting Dataset-JSON format instead of SAS XPT
- As the R-based serialization step in a reproducible submission pipeline (e.g., Pilot 5 workflow)
- When converting a legacy XPT-based submission package to Dataset-JSON for re-submission

### Limitations

- **Decimal precision**: floating-point R variables require explicit casting to decimal string representation before writing; a wrapper function is needed to enforce consistency (as encountered in Pilot 5)
- **Metadata requirements**: variable labels must be set explicitly on the data frame (e.g., `attr(df, "label")`) before creating the Dataset-JSON object — R's data.frame natively does not carry labels
- **Ongoing issues**: some limitations remain under active development by the Atorus team (see GitHub issues)

### Connections

- Implements: [[Dataset-JSON]] standard (v1.0 and v1.1)
- Used in: R Consortium Submissions Pilot 5 — documented in [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]]
- Maintained by: Atorus Research (also maintains `{tfrmt}`, `{metacore}`, `{xportr}` in the Pharmaverse ecosystem)
- Related entity: [[R Consortium Submissions Working Group]]
- Related topic: [[Regulatory Data Submission Standards]]
