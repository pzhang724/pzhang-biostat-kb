---
title: "Analysis Results Data"
type: concept
tags: [ard, ardm, cdisc, clinical-reporting, reproducibility, reusability, analysis-results-standard]
created: 2026-04-30
updated: 2026-04-30
sources: 3
---

# Analysis Results Data

## Definition

**Analysis Results Data (ARD)** is the concept of treating the numerical outputs of statistical analyses — estimates, confidence intervals, p-values, counts, model parameters — as structured, machine-readable data objects, rather than as rendered visual artifacts (plots, Word tables, PDF reports). Storing results as tidy, linked data enables reuse, reproducibility, and programmatic access without re-running analyses.

Two related but distinct frameworks use this term:

1. **CDISC Analysis Results Standard** — the formal regulatory standard under development; implemented in the `{cards}` R package
2. **Analysis Results Data Model (ARDM)** — an academic proposal by Marques-Barros, Widmer, Baillie (Novartis/Idorsia) focusing on a principled data model for results + contextual metadata; distinct from but informed by the CDISC standard

## Motivation

The prevailing assumption in clinical and scientific analysis is that a result is its presentation: a Kaplan-Meier plot, a forest table in a PDF. This creates serious downstream problems:

- **Reproducibility**: without the underlying data, reproducing a figure requires reverse-engineering it (digitizing survival curves pixel by pixel)
- **Reuse**: reformatting a plot for a different journal requires re-running the entire analysis
- **Automation**: medical writers must manually copy-paste numbers from outputs into reports
- **Cross-study synthesis**: meta-analysis is blocked when individual-study results exist only as images

Treating results as data — structured, labeled, linked to their provenance — resolves all of these.

## ARDM Design Principles (Marques-Barros et al.)

The ARDM paper proposes six principles a well-designed analysis results data model should satisfy:

| Principle | Meaning |
|-----------|---------|
| **Searchable** | Results queryable via consistent APIs/databases |
| **Non-redundant** | Validated results stored once; reused without re-derivation |
| **Separation of concerns** | Results, metadata, study info, output specs stored in separate linked tables |
| **Reproducible** | Enough contextual metadata to re-run the analysis from scratch |
| **Interoperable** | Language-agnostic format; results from R, SAS, Python fit the same schema |
| **Community-driven** | Standard shaped by practitioner consensus, not imposed top-down |

## CDISC Implementation (`{cards}`)

The `{cards}` package creates ARD objects as long-format data frames:

```r
ard_summary(ADSL, by = "ARM", variables = "AGE")
# group1  group1_level  variable  stat_name  stat_label  stat
# ARM     Placebo       AGE       N          N           86
# ARM     Placebo       AGE       mean       Mean        75.21
# ARM     Placebo       AGE       sd         SD          8.59
# ...
```

Each row contains: grouping variable + level, analysis variable, statistic name/label, value, formatting function, and any warnings/errors. The `{cardx}` extension adds model-based statistics (t-tests, regression, MMRM).

## Data Model Structure (ARDM)

A minimal ARDM for a Kaplan-Meier plot uses four linked tables:

| Table | Content |
|-------|---------|
| `studies` | Study identifier, arms |
| `demographic_variables` | Variable name, units, CDISC column mapping |
| `analysis_metadata` | Software, packages, function calls, R version; links to results and output |
| `survival_ard` | Survival estimates, CIs, events, strata — the actual ARD |

## OMOP CDM as Proof of Concept

The OMOP Common Data Model demonstrates what community consensus on a data model achieves for observational health data — standardized, queryable, globally reused. ARDM proponents cite OMOP as the aspirational benchmark for what a mature ARD ecosystem could achieve for clinical trial analysis results.

## Assumptions and Limitations

- The full value of ARD requires that *all* analyses produce ARD-format output — ad hoc or legacy analyses may not fit
- Contextual metadata capture (e.g., decisions made during analysis evolution) requires cultural change, not just tooling
- The CDISC standard and ARDM academic proposal are complementary but not identical; regulatory adoption timelines are uncertain

## Connections

- Implemented by: [[cards R Package]], [[cardx R Package]]
- Consumed by: [[gtsummary R Package]] (rendering), [[ARD-Based Clinical Reporting]] (topic)
- Input standards: [[CDISC ADaM]], [[CDISC SDTM]]
- Sources: [[A Case-Study Driven Motivation of Analysis Results Data]], [[Analysis Results Data ({cards})]], [[Extra Analysis Results Data Utilities ({cardx})]]
