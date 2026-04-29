---
title: "Group Sequential Design"
type: concept
tags: [group-sequential, adaptive-design, interim-analysis, clinical-trials, alpha-spending, survival]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# Group Sequential Design

A class of adaptive clinical trial designs that allow pre-specified interim analyses — with potential for early stopping for efficacy or futility — while controlling the overall type I error rate through alpha-spending functions.

## Overview

In a conventional fixed-sample trial, the final analysis is performed once after all data are collected. Group sequential designs (GSDs) instead pre-specify one or more **interim analyses** at which accumulating data can be examined. This enables:
- **Early stopping for efficacy**: if overwhelming evidence of benefit emerges, the trial can stop early, exposing fewer patients to an inferior treatment and accelerating drug access
- **Early stopping for futility**: if interim data make the final analysis unlikely to succeed, resources can be redirected
- **Safety monitoring**: ongoing assessment of accumulating adverse event data

The challenge with multiple looks at the data is **alpha inflation** — repeated hypothesis testing inflates the type I error rate. GSDs solve this using **alpha-spending functions** (or **error spending functions**) that allocate portions of the total alpha budget across interim and final analyses, controlling the familywise error rate at the pre-specified level.

## Formal Definition

Let $Z_k$ be the test statistic at interim $k = 1, \ldots, K$, based on information fraction $t_k = n_k / N$ where $n_k$ is the cumulative sample size and $N$ is the maximum sample size. The boundaries $\{c_k\}$ are chosen so that:

$$P(Z_1 > c_1 \text{ or } Z_2 > c_2 \text{ or } \ldots \text{ or } Z_K > c_K \mid H_0) = \alpha$$

**Common alpha-spending functions** $f(t)$ (cumulative alpha spent through information fraction $t$):
- **O'Brien-Fleming (OBF)**: $f(t) = 2 - 2\Phi(z_{\alpha/2}/\sqrt{t})$ — very conservative at early interims, preserves near-nominal boundary at final
- **Pocock**: $f(t) = \alpha \cdot \log(1 + (e-1)t)$ — equal boundaries at each look, easier to achieve early stopping but penalizes the final boundary
- **Kim-DeMets (power family)**: $f(t) = \alpha \cdot t^\rho$, $\rho > 0$ — flexible; $\rho = 1$ gives linear spending

**Futility boundaries** use analogous beta-spending functions; can be **binding** (mandatory stopping) or **non-binding** (advisory).

## Key Assumptions

- **Pre-specification**: boundaries must be fixed in the study protocol before unblinding; ad-hoc interim looks inflate type I error
- **Independent increments**: test statistics at successive interims must follow approximately the canonical joint normal distribution (satisfied by common test statistics under standard regularity conditions)
- **Information fractions**: accurate prediction of final information (e.g., number of events in survival trials) is required to place interims correctly; actual timing may differ from planned

## Estimation

GSDs are planned using software; the R Consortium pharma-skills repository provides an agent skill specifically for survival endpoint GSD.

## Software

| Package | Language | Key Function | Notes |
|---------|----------|--------------|-------|
| `{gsDesign}` | R | `gsDesign()` | Flexible alpha-spending, OBF/Pocock/custom |
| `{rpact}` | R | `getDesignGroupSequential()` | Comprehensive; CRAN; regulatory-grade |
| `{gsd}` | R | — | Bayesian GSD extensions |
| East | SAS/standalone | — | Industry standard; East 7 widely used |
| SAS `PROC SEQDESIGN` | SAS | `PROC SEQDESIGN` | Native SAS implementation |

See [[CAMIS Working Group]] for R vs SAS vs East comparisons on GSD for survival endpoints.

## Variants / Extensions

- **Lan-DeMets spending function**: allows alpha-spending function to be specified continuously — interims can occur at any information fraction without pre-specifying exact timing
- **Adaptive GSD**: allows sample size re-estimation at interim based on observed effect size; requires pre-specification of the adaptation rule
- **Platform trials**: seamless entry/exit of arms in a master protocol; GSD boundaries require adjustment for multiple hypotheses
- **Bayesian GSD**: uses posterior probability thresholds rather than frequentist boundaries; see `{gsd}` and `{RBesT}`

## Connections

- Related concept: multiple testing and family-wise error rate control
- Applied to: survival endpoints — [[CAMIS Working Group]] documents R/SAS/East comparisons
- Agent skill: [[R Consortium pharma-skills — BioPharma Agent Skills]]
- Design context: ICH E9(R1) estimands framework shapes what the GSD is testing
- Related concept: adaptive designs (broader category including GSD, sample size re-estimation, seamless phase designs)

## Common Pitfalls

- **Unplanned interim looks**: even informal data reviews by unblinded personnel can be treated as additional looks under FDA scrutiny
- **Information fraction mismatch**: in survival trials, events accumulate unevenly; if the interim occurs at a different information fraction than planned, the boundary must be recalculated using the alpha-spending function (not the original boundary)
- **Binding vs non-binding futility**: non-binding futility boundaries are more common in practice (they don't inflate alpha if not followed) but require explicit justification in the SAP
- **Multiplicity with secondary endpoints**: alpha-spending for primary endpoint does not protect secondary endpoints tested at the same interims

## Key References

- [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]] — R/SAS/East comparison for GSD with survival endpoints
- [[R Consortium pharma-skills — BioPharma Agent Skills]] — agent skill for GSD design automation
