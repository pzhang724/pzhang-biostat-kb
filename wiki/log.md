# Wiki Log

Append-only chronological record of all wiki activity.

**Grep tips:**
```bash
grep "^## \[" wiki/log.md              # all entries
grep "^## \[" wiki/log.md | tail -10   # last 10 entries
grep "ingest" wiki/log.md              # all ingests
grep "lint" wiki/log.md                # all lint passes
```

---

## [2026-04-27] setup | Initial wiki scaffolding

- Pages created: `wiki/index.md`, `wiki/log.md`
- Templates created: `wiki/templates/source-summary.md`, `wiki/templates/concept-page.md`, `wiki/templates/entity-page.md`, `wiki/templates/topic-page.md`
- Schema created: `CLAUDE.md`
- Notes: Repository initialized with the LLM Wiki pattern based on Andrej Karpathy's gist. Domain: biostatistics.

---

## [2026-04-27] ingest | Karpathy — LLM Wiki Pattern

- Source: `raw/sources/karpathy-llm-wiki.md`
- Pages created: `wiki/sources/karpathy-llm-wiki-pattern.md`, `wiki/concepts/llm-wiki-pattern.md`, `wiki/entities/andrej-karpathy.md`
- Pages updated: `wiki/index.md`
- Notes: Founding source for this wiki's architecture. The LLM Wiki pattern itself is the meta-framework governing how this knowledge base operates. No biostatistics content yet — this is purely infrastructure.

---

## [2026-04-27] ingest | SDTM Programming in R using {sdtm.oak} Package

- Source: `raw/SDTM programming in R using {sdtm.oak} package.md`
- Pages created: `wiki/sources/sdtm-oak-r-in-pharma-workshop.md`, `wiki/concepts/cdisc-sdtm.md`, `wiki/concepts/sdtm-oak.md`, `wiki/entities/sdtm-oak-r-package.md`, `wiki/entities/pharmaverse.md`, `wiki/entities/rammprasad-ganapathy.md`
- Pages updated: `wiki/index.md`
- Notes: First biostatistics/clinical data content in the wiki. Source is a 95KB YouTube workshop transcript (R in Pharma 2026). Key contribution: detailed coverage of all 8 sdtm.oak algorithms and the OKD variable concept. Lab unit standardization flagged as an open gap. Raw file is in `raw/` (not `raw/sources/`) — consider moving for consistency.

---

## [2026-04-29] ingest | Batch ingest — 12 sources (regulatory, R validation, data standards, clinical design)

- Sources (12):
  - `raw/sources/Sponsor Responsibilities - Safety Reporting Requirements and Safety As.md`
  - `raw/sources/Study Data Technical Conformance Guide.md`
  - `raw/sources/Oncology Therapeutic Radiopharmaceuticals Dosage Optimization.md`
  - `raw/sources/Breaking Free from the XPT Exploration of Dataset-JSON...md`
  - `raw/sources/pharmaR website.md`
  - `raw/sources/What is GxP Validation in Clinical Software Development.md`
  - `raw/sources/Emily Yates - Code that Cures Validating GxP-Compliant R Shiny Apps for Clinical Decisions.md`
  - `raw/sources/Validated.md`
  - `raw/sources/GSWEP4R Workshop - 3 An R Package Engineering Workflow.md`
  - `raw/sources/CAMIS - A PHUSE DVOST Working Group.md`
  - `raw/sources/openstatsware.md`
  - `raw/sources/RConsortiumpharma-skills A collection of agent skills for BioPharma use cases.md`
- Pages created (25):
  - Sources: `wiki/sources/sponsor-responsibilities-ind-safety-reporting.md`, `wiki/sources/fda-study-data-technical-conformance-guide.md`, `wiki/sources/fda-guidance-radiopharmaceutical-dosage-optimization.md`, `wiki/sources/breaking-free-from-xpt-dataset-json.md`, `wiki/sources/pharmar-r-validation-hub.md`, `wiki/sources/gxp-validation-clinical-software-appsilon.md`, `wiki/sources/emily-yates-validating-gxp-r-shiny-apps.md`, `wiki/sources/posit-validated-r-package-strategy.md`, `wiki/sources/gswep4r-workshop-r-package-engineering-workflow.md`, `wiki/sources/camis-phuse-cross-language-statistical-comparisons.md`, `wiki/sources/openstatsware-working-group.md`, `wiki/sources/rconsortium-pharma-skills.md`
  - Concepts: `wiki/concepts/dataset-json.md`, `wiki/concepts/gxp-validation.md`, `wiki/concepts/ind-safety-reporting.md`, `wiki/concepts/group-sequential-design.md`
  - Entities: `wiki/entities/camis.md`, `wiki/entities/openstatsware.md`, `wiki/entities/r-validation-hub.md`, `wiki/entities/riskmetric-r-package.md`, `wiki/entities/datasetjson-r-package.md`, `wiki/entities/r-consortium-submissions-working-group.md`
  - Topics: `wiki/topics/r-validation-in-regulated-environments.md`, `wiki/topics/regulatory-data-submission-standards.md`, `wiki/topics/cross-language-statistical-implementations.md`
- Pages updated: `wiki/concepts/cdisc-sdtm.md`, `wiki/entities/pharmaverse.md`, `wiki/index.md`
- Skipped (7): `Restaurant tipping.md` (demo data), `SCE WHITE PAPER.md` (empty body), `Anthropic Courses.md` (course listing), `alchaincyf/claude-code-orange-book` (off-topic), `alchaincyf/obsidian-ai-orange-book` (off-topic), `pharmaR website 1.md` (duplicate), `RConsortiumpharma-skills...1.md` (duplicate)
- Notes: Large batch; three thematic clusters emerged — (1) R validation ecosystem (pharmaR, GxP, GSWEP4R, Emily Yates, Posit validated) synthesized into R validation topic; (2) data submission standards (SDTM, Dataset-JSON, XPT, FDA conformance) synthesized into regulatory submission topic; (3) cross-language statistical implementations (CAMIS) as a topic. Dataset-JSON Pilot 5 is particularly notable — first public R submission using JSON transport, eCTD submitted Fall 2025. CAMIS covers 60+ methods and is an excellent quick-reference for R/SAS/Python discrepancies. Group Sequential Design concept created based on RConsortium pharma-skills and CAMIS coverage; can be expanded when more GSD-specific sources are ingested.

---

## [2026-04-30] ingest | Batch ingest — 28 new sources (TLG pipeline, ARD, Shiny testing, Git, regulatory)

- Sources (28):
  - `raw/sources/A Case-Study Driven Motivation of Analysis Results Data.md`
  - `raw/sources/ADaM in R Asset Library.md`
  - `raw/sources/Analysis Results Data.md`
  - `raw/sources/Applied Longitudinal Analysis.md`
  - `raw/sources/CAMIS - A PHUSE DVOST Working Group 1.md`
  - `raw/sources/Create Common TLGs Used in Clinical Trials.md`
  - `raw/sources/Explore the Pharmaverse Examples Your Gateway to Clinical Reporting with Open-Source Tools.md`
  - `raw/sources/Extra Analysis Results Data Utilities.md`
  - `raw/sources/Faster Clinical Trial Reporting A Beginner's Guide to Implementing CDISC SDTM and ADaM Standards with Open-Source R Packages.md`
  - `raw/sources/GxP Validation in Software Development starts from the Definition of Done.md`
  - `raw/sources/Happy Git and GitHub for the useR.md`
  - `raw/sources/How to Write Robust shinytest2 Tests for R Shiny Apps.md`
  - `raw/sources/Introduction to Chevron.md`
  - `raw/sources/Introduction – R Submissions Working Group.md`
  - `raw/sources/Outstanding User Interfaces with Shiny.md`
  - `raw/sources/Paradigm Health Announces Collaboration with the FDA to Transform Regulatory Review of Clinical Trial Data.md`
  - `raw/sources/Presentation-Ready Data Summary and Analytic Result Tables.md`
  - `raw/sources/Python for Clinical Study Reports and Submission.md`
  - `raw/sources/Reporting Tables.md`
  - `raw/sources/Shiny testing overview.md`
  - `raw/sources/Study Data for Submission to CDER and CBER.md`
  - `raw/sources/TLG Catalog.md`
  - `raw/sources/Test Coverage for Packages.md`
  - `raw/sources/The Composer of Plots.md`
  - `raw/sources/Version Control with Git & RStudio.md`
  - `raw/sources/What LLMs Actually Do (and What They Don't).md`
  - `raw/sources/r4sub — Ready for Submission.md`
  - `raw/sources/teal Modules for Standard Clinical Outputs.md`
- Pages created (47):
  - Sources (28): `wiki/sources/ardm-case-study-workshop-2023.md`, `wiki/sources/admiral-r-package-docs.md`, `wiki/sources/cards-ard-package.md`, `wiki/sources/cardx-ard-extensions.md`, `wiki/sources/pharmaverse-examples-2025.md`, `wiki/sources/faster-clinical-reporting-pharmaverse.md`, `wiki/sources/tern-tlg-package.md`, `wiki/sources/rtables-package.md`, `wiki/sources/chevron-tlg-framework.md`, `wiki/sources/gtsummary-package.md`, `wiki/sources/teal-modules-clinical.md`, `wiki/sources/tlg-catalog-nest.md`, `wiki/sources/patchwork-composer-of-plots.md`, `wiki/sources/appsilon-gxp-definition-of-done.md`, `wiki/sources/shiny-testing-overview.md`, `wiki/sources/shinytest2-robust-testing.md`, `wiki/sources/covr-test-coverage.md`, `wiki/sources/happy-git-with-r.md`, `wiki/sources/version-control-git-rstudio-workshop.md`, `wiki/sources/outstanding-shiny-ui.md`, `wiki/sources/r-submissions-wg-intro.md`, `wiki/sources/study-data-cder-cber.md`, `wiki/sources/paradigm-health-fda-2026.md`, `wiki/sources/r4sub-submission-readiness.md`, `wiki/sources/camis-method-repository.md`, `wiki/sources/pycsr-python-for-csr.md`, `wiki/sources/what-llms-actually-do.md`, `wiki/sources/applied-longitudinal-analysis.md`
  - Concepts (3): `wiki/concepts/analysis-results-data.md`, `wiki/concepts/cdisc-adam.md`, `wiki/concepts/shiny-testing.md`
  - Entities (13): `wiki/entities/admiral-r-package.md`, `wiki/entities/cards-r-package.md`, `wiki/entities/cardx-r-package.md`, `wiki/entities/tern-r-package.md`, `wiki/entities/rtables-r-package.md`, `wiki/entities/gtsummary-r-package.md`, `wiki/entities/chevron-r-package.md`, `wiki/entities/teal-r-package.md`, `wiki/entities/patchwork-r-package.md`, `wiki/entities/covr-r-package.md`, `wiki/entities/r4sub-r-package.md`, `wiki/entities/shinytest2-r-package.md`, `wiki/entities/jenny-bryan.md`
  - Topics (3): `wiki/topics/ard-based-clinical-reporting.md`, `wiki/topics/tlg-production-pipeline-r.md`, `wiki/topics/shiny-app-testing-pharma.md`
- Pages updated (8): `wiki/entities/pharmaverse.md` (added 8 packages, updated sources to 4), `wiki/entities/R Consortium Submissions Working Group.md` (added Pilots 6 & 7, sources to 2), `wiki/entities/CAMIS Working Group.md` (66+ methods, added second source), `wiki/topics/R Package Validation in Regulated Environments.md` (added Shiny testing section and table, sources to 9), `wiki/topics/Regulatory Data Submission Standards.md` (added FDA technical requirements, r4sub, Paradigm Health sections, sources to 7), `wiki/topics/Cross-Language Statistical Implementations (R, SAS, Python).md` (added CAMIS method repository reference, sources to 2), `wiki/index.md`, `wiki/log.md`
- Notes: Five thematic clusters in this batch — (1) full CDISC TLG pipeline in R (tern/rtables/chevron/teal/gtsummary/patchwork) synthesized into TLG Production Pipeline topic; (2) ARD-based reporting (ARDM workshop, cards, cardx) synthesized into ARD-Based Clinical Reporting topic; (3) Shiny app testing in pharma (shinytest2, covr, Appsilon DoD, Emily Yates) synthesized into Shiny App Testing in Pharma topic; (4) Git/version control (Happy Git, RStudio workshop) as entity/source pages; (5) regulatory submissions (FDA study data page, r4sub, Paradigm Health 2026 real-time review). Notable items: Paradigm Health FDA collaboration announced April 28, 2026 — first public real-time continuous regulatory review using AI (potentially transformative). Pilots 6 & 7 confirmed in r-submissions-wg-intro source. CAMIS now documented at 66+ methods. Applied Longitudinal Analysis source was essentially empty (URL-only clip); created minimal stub. Outstanding Shiny UI was also sparse but documented. Total wiki now 42 sources, 81 pages.
