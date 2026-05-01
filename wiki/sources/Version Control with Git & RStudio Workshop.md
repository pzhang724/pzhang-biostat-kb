---
title: "Version Control with Git & RStudio Workshop"
type: source
tags: [git, version-control, rstudio, r-pharma, camis, branching, merging, clinical-data]
created: 2026-04-30
updated: 2026-04-30
sources: 1
---

# Version Control with Git & RStudio Workshop

**Raw file**: `raw/sources/Version Control with Git & RStudio.md`  
**Author(s)**: Christina Fillmore (GSK), Alexandra Lauer (Merck KGaA), Lyn Taylor (Paraxel), Irene Vassallo (Incyte)  
**Year**: 2023  
**Type**: talk  
**Venue**: R/Pharma Workshop Series, October 17, 2023

## Summary

Hands-on workshop introducing Git and GitHub for pharma statisticians and data scientists using RStudio and a Shiny app for interactive exercises. Uses the narrative of statistician "Camille" managing journal submissions to motivate branching, tagging, and merging. Instructors are all pharma practitioners who came to Git through the CAMIS project.

## Key Points

- **Repository**: folder + hidden `.git/` tracking directory; a repo is the unit of what's tracked together
- **Commit**: snapshot of file *changes* (not whole files); can span multiple files; commit messages should describe *why*, not just what; recommended <80 characters
- **Checkout**: moving between commits or branches (changing your HEAD position)
- **Branch**: non-linear parallel line of changes; branch from any commit; unlimited branches/commits
- **Tag**: named pointer to a specific commit; useful for marking publication/submission versions
- **Merge**: combine branch changes back into main; conflicts occur when same lines changed in both branches
- **Pharma context**: CAMIS project itself was the motivation for creating this Git training — need for reproducible collaborative statistical repositories
- Resources: CAMIS Git training app (camis.shinyapps.io/git-app/), git-training GitHub repos

## Methods / Concepts Covered

- [[GxP Validation]] — version control (audit trail, change tracking) is a core GxP requirement
- [[Cross-Language Statistical Implementations (R, SAS, Python)]] — CAMIS uses git for its collaborative repository

## Connections

- Related source: [[Happy Git and GitHub for the useR]], [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]]
- Related entity: [[CAMIS Working Group]]
- Relevant to: [[R Package Validation in Regulated Environments]]
