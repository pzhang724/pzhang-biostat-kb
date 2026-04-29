---
title: "IND Safety Reporting"
aliases: ["IND Safety Reporting"]
type: concept
tags: [fda, regulatory, safety, pharmacovigilance, ind, clinical-trials, adverse-events]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# IND Safety Reporting

The regulatory framework under which clinical trial sponsors must report serious and unexpected adverse drug reactions to the FDA during investigational new drug (IND) studies, as governed by 21 CFR 312.32.

## Overview

Before a pharmaceutical company can conduct clinical trials in the US, they must hold an active IND application with the FDA. A core IND obligation is **safety reporting**: the sponsor must monitor accumulating safety data and report significant findings to the FDA on defined timelines. This enables the FDA to protect trial participants by suspending or modifying studies when unanticipated safety signals emerge.

The reporting framework distinguishes between:
- **Expedited reports**: submitted within 7 or 15 calendar days for serious unexpected suspected adverse reactions (SUSARs)
- **IND Annual Reports**: yearly comprehensive safety summaries
- **Aggregate data assessments**: periodic review of all safety information across the IND program (two specific provisions in 21 CFR 312.32)

The decision to file an expedited report involves three assessments: (1) Is the event **serious**? (2) Is it **unexpected** (not described in the Investigator's Brochure)? (3) Is there a **reasonable possibility** it is causally related to the study drug?

## Formal Definition

**Serious adverse event (SAE)**: An event that results in death, is immediately life-threatening, requires inpatient hospitalization or prolongation of existing hospitalization, results in persistent or significant disability/incapacity, is a congenital anomaly/birth defect, or is an important medical event requiring medical intervention to prevent one of the above outcomes.

**Unexpected**: Not consistent with the risk information currently described in the Investigator's Brochure (IB). New or more frequent occurrence than described in the IB qualifies as unexpected.

**Reporting timelines**:
- **7-day report**: fatal or immediately life-threatening unexpected SAR with reasonable possibility of causal relationship
- **15-day report**: all other unexpected SARs with reasonable possibility of causal relationship

## Key Assumptions

- **Causality is sponsor's judgment**: FDA does not require certainty of causation — "reasonable possibility" is a low bar, erring on the side of reporting
- **IB is the reference**: unexpectedness is assessed against the current IB, which must be kept current
- **Aggregate assessment is required**: sponsors must not only report individual events but also periodically assess whether patterns in accumulating safety data suggest a new signal

## Software

| Tool | Purpose |
|------|---------|
| Argus Safety, Veeva Vault | Industry-standard pharmacovigilance databases for case management |
| `{tern}` (Pharmaverse) | R package for adverse event summarization tables |
| R safety analysis ADaMs | ADAE, ADSL domains from SDTM provide the data substrate |

## Variants / Extensions

- **BA/BE studies**: bioavailability/bioequivalence studies under IND have specific safety reporting requirements covered in the same FDA guidance
- **Post-market (FAERS)**: once approved, adverse event reporting transitions from IND framework to MedWatch/FAERS under 21 CFR Part 314
- **EU**: equivalent framework under EMA Clinical Trials Regulation (EU CTR) and EudraVigilance

## Connections

- Governed by: 21 CFR 312.32; FDA Guidance on Sponsor Responsibilities
- Data substrate: [[CDISC SDTM]] ADAE domain contains adverse event data for aggregate analysis
- Source: [[Sponsor Responsibilities — IND Safety Reporting]]
- Related topic: [[Regulatory Data Submission Standards]]

## Common Pitfalls

- **Under-reporting due to causality uncertainty**: sponsors sometimes withhold 15-day reports because causality is unclear; "reasonable possibility" sets a deliberately low threshold
- **IB lag**: failing to update the IB when safety information accumulates means unexpected events are assessed against outdated expectations
- **Aggregate review timing**: the two aggregate data assessment provisions in 21 CFR 312.32 are sometimes overlooked in favor of individual-event reporting only

## Key References

- [[Sponsor Responsibilities — IND Safety Reporting]] — FDA guidance document covering all expedited reporting requirements
