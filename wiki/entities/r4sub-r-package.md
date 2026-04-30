---
title: "r4sub R Package"
type: entity
tags: [r-package, submission-readiness, fmea, traceability, regulatory, sci]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# r4sub R Package

## R Package

**Language**: R  
**CRAN**: `install.packages("r4sub")`  
**Repo**: github.com/R4SUB/r4sub  
**Maintained by**: R4SUB team  
**Primary use**: Assessing and documenting clinical submission readiness (Submission Confidence Index)

### Package Ecosystem

| Package | Role |
|---------|------|
| `r4subcore` | Evidence schema, scoring primitives, parsers |
| `r4subtrace` | ADaM/SDTM variable-level traceability engine |
| `r4subscore` | Submission Confidence Index (SCI) scoring |
| `r4subrisk` | FMEA-based risk quantification |
| `r4subdata` | Example datasets |
| `r4subprofile` | Regulatory submission profiles (FDA/EMA) |
| `r4subusability` | Label quality, Define-XML, annotation indicators |
| `r4subui` | Optional interactive Shiny dashboard |

### Key Workflow

```r
library(r4sub)
data(evidence_pharma)
scores <- compute_indicator_scores(evidence_pharma)
sci    <- compute_sci(compute_pillar_scores(scores))
```

### When to Use

- End-to-end submission readiness assessment before NDA/BLA filing
- Quantifying and documenting FMEA risks across the data pipeline
- Generating traceability evidence from ADaM variable derivations

### Connections

- Complements: [[riskmetric R Package]] (package-level risk) — r4sub adds submission-level risk
- Related concept: [[GxP Validation]], [[CDISC ADaM]]
- Source: [[r4sub — Ready for Submission]]
- Related topic: [[Regulatory Data Submission Standards]]
