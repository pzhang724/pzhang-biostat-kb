---
title: "Wiki Index"
type: meta
updated: 2026-04-30
total_sources: 42
total_pages: 81
---

# Wiki Index

Master catalog of all pages in this knowledge base. Updated on every ingest.

**Quick stats**: 42 sources ingested · 81 wiki pages · last updated 2026-04-30

**Navigation tip**: Read this file first when answering a query. Find relevant pages, then drill in.

---

## Sources

Source summary pages — one per raw document ingested.

### Foundations / Meta
- [[Karpathy — LLM Wiki Pattern]] — Andrej Karpathy's gist describing the LLM Wiki architecture: persistent wiki maintained by LLM, replacing RAG for personal knowledge bases (1 source)
- [[What LLMs Actually Do (and What They Don't)]] — Posit blog by Eeftink explaining LLM concepts (tokens, attention, hallucination, RAG, fine-tuning) for R/Python programmers without ML background (1 source)

### CDISC Data Pipeline
- [[SDTM programming in R using {sdtm.oak} package]] — R in Pharma 2026 workshop by Rammprasad Ganapathy (Roche) covering all 8 sdtm.oak algorithms with worked examples across CM, VS, AE, DM domains (1 source)
- [[ADaM in R Asset Library]] — {admiral} package documentation; TA extension family (oncology, immunology, vaccines, respiratory); four design principles (usability, simplicity, findability, readability) (1 source)
- [[A Case-Study Driven Motivation of Analysis Results Data]] — R/Pharma 2023 workshop by Marques-Barros, Widmer, Baillie (Novartis/Idorsia); six ARDM principles; KM table case study demonstrating ARD separation of computation from presentation (1 source)
- [[Analysis Results Data ({cards})]] — {cards} R package documentation; CDISC ARS implementation; ard_summary() output format; ARD as long-format table (1 source)
- [[Extra Analysis Results Data Utilities ({cardx})]] — {cardx} R package documentation; model-based ARDs: t-tests, MMRM, Cox, regression, survey stats; extends {cards} (1 source)

### TLG Production
- [[Explore the Pharmaverse Examples (2025)]] — Doyle & Farrugia 2025 blog; pharmaverse.github.io/examples end-to-end worked clinical reporting examples (1 source)
- [[Faster Clinical Trial Reporting — Pharmaverse Beginner Guide]] — Fabian Hee 2025 blog; beginner walkthrough of CDASH→SDTM→ADaM→TLG pipeline with Pharmaverse packages (1 source)
- [[Create Common TLGs Used in Clinical Trials ({tern})]] — {tern} package documentation; visualization catalog (g_km, g_forest, g_waterfall); analysis functions and summarize_coxreg (1 source)
- [[Reporting Tables ({rtables})]] — {rtables} package documentation; layout API; design principle of cell values separate from display strings; cell formatting functions (1 source)
- [[Introduction to Chevron ({chevron})]] — {chevron} package documentation; S4 architecture with preprocess/main/postprocess slots; run() interface; GDS naming convention (1 source)
- [[Presentation-Ready Data Summary and Analytic Result Tables ({gtsummary})]] — {gtsummary} package documentation; tbl_summary(), tbl_regression(), inline_text(); ARD integration; output format support (gt, flextable, kableExtra) (1 source)
- [[teal Modules for Standard Clinical Outputs ({teal.modules.clinical})]] — {teal.modules.clinical} documentation; patient profile modules; Shinylive demos; GxP use cases (1 source)
- [[TLG Catalog (NEST)]] — insightsengineering TLG Catalog; Quarto-based reference; 100+ standard TLGs; stable/development profiles; daily CI/CD rebuild (1 source)
- [[The Composer of Plots ({patchwork})]] — {patchwork} R package documentation; `+`/`/`/`|` operators for composing ggplot2 multi-panel figures (1 source)

### Shiny App Testing
- [[GxP Validation in Software Development Starts from the Definition of Done (Appsilon)]] — Appsilon blog using Scrum DoD as living GxP checklist; IQ/OQ/PQ; traceability, accountability, data integrity pillars (1 source)
- [[Shiny Testing Overview]] — Posit documentation; three-tier taxonomy (unit/server/snapshot); GxP relevance of each layer; overview of shinytest2 and shinyloadtest (1 source)
- [[How to Write Robust shinytest2 Tests for R Shiny Apps]] — Sobolewski 2025 guide; data-testid/data-testtype pattern; custom ShinyDriver R6 class; step functions for behavior-focused test language (1 source)
- [[Test Coverage for Packages ({covr})]] — {covr} R package documentation; report(), zero_coverage(), # nocov exclusions; GitHub Actions integration; GxP dossier use (1 source)
- [[Outstanding User Interfaces with Shiny]] — David Granjon book; advanced Shiny UI customization; input/output patterns; CSS and JavaScript integration (1 source)

### Version Control / Git
- [[Happy Git and GitHub for the useR]] — Jenny Bryan & Jim Hester; definitive practical Git guide for R data scientists; daily workflows, branching, GitHub, troubleshooting (1 source)
- [[Version Control with Git & RStudio Workshop]] — R/Pharma 2023 workshop by Fillmore, Lauer, Taylor, Vassallo; Git concepts for pharma R users: commits, branches, merging, pull requests (1 source)

### Regulatory Submissions
- [[Introduction — R Submissions Working Group]] — R Consortium WG homepage; 7 pilots (Pilots 6 & 7 launched 2026); mission of demonstrating R-based FDA submissions (1 source)
- [[Study Data for Submission to CDER and CBER (FDA)]] — FDA CDER/CBER submission page; Technical Rejection Criteria; required standards (SDTMIG, ADaMIG, SEND, define.xml); Dataset-JSON acceptability (1 source)
- [[Paradigm Health — FDA Real-Time Review Collaboration (2026)]] — April 28, 2026 press release; Paradigm Health + FDA AI platform for real-time continuous regulatory review; partners: Amgen, AstraZeneca, MD Anderson, UPenn (1 source)
- [[r4sub — Ready for Submission]] — {r4sub} R meta-package; SCI scoring (Submission Compliance Index); FMEA risk assessment; traceability engine; submission readiness checklist (1 source)

### Statistical Methods
- [[Sponsor Responsibilities — IND Safety Reporting]] — FDA guidance on IND expedited safety reporting (7-day/15-day reports), causality assessment, and aggregate data provisions under 21 CFR 312.32 (1 source)
- [[FDA Study Data Technical Conformance Guide]] — FDA technical specifications for electronic study data submissions: SDTM, ADaM, define.xml, file formats, and Pinnacle 21 validation requirements (1 source)
- [[FDA Guidance — Oncology Radiopharmaceutical Dosage Optimization]] — FDA guidance for sponsors identifying optimized dosage (administered activity + schedule) for radiopharmaceutical therapies in oncology clinical development (1 source)
- [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]] — PHUSE paper arguing for Dataset-JSON v1.1 as XPT replacement; documents R Consortium Submission Pilot 5 (full R pipeline, all datasets as Dataset-JSON, submitted Fall 2025) (1 source)
- [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]] — PHUSE DVOST living reference repository: 60+ statistical methods compared across R, SAS, and Python with discrepancy explanations; regulatory motivation (1 source)
- [[CAMIS — Method Repository Page]] — CAMIS full methods repository; 66+ methods with detailed category-by-category status including MMRM, GSD, causal inference, and Python coverage (1 source)
- [[Python for Clinical Study Reports and Submission]] — pycsr.org book by Yilong Zhang; Python-based clinical study reports; ICH E3 structure; growing Python in pharma context (1 source)
- [[Applied Longitudinal Analysis]] — Fitzmaurice, Laird, Ware textbook; foundational reference for longitudinal/repeated measures statistical methods (1 source)

### R Validation Ecosystem
- [[pharmaR — The R Validation Hub]] — overview of the R Validation Hub: `{riskmetric}`, `{riskassessment}`, risk-based white paper, and regulatory R repository initiative (1 source)
- [[GxP Validation in Clinical Software Development (Appsilon)]] — practical overview of all GxP domains (CGMP, GLP, GCP, GAMP) and seven good software engineering practice areas for FDA/EMA submission software (1 source)
- [[Emily Yates — Validating GxP-Compliant R Shiny Apps]] — R/Pharma 2024 talk by Emily Yates (Formation Bio): three-pillar GxP validation framework for clinical R Shiny apps — validated environment, risk-based packages, GAMP 5-aligned SDLC (1 source)
- [[Posit — Validated R Package Strategy]] — Posit documentation: creating a controlled, audit-ready internal R package repository using Posit Package Manager and `{renv}` for regulated environments (1 source)
- [[GSWEP4R Workshop — R Package Engineering Workflow]] — openstatsware workshop slide deck: professional vs. anti-pattern R package development workflows; SDLC rationale grounded in empirical cost/error data (1 source)
- [[openstatsware — Statistical Software Engineering Working Group]] — overview of the ASA/PSI/EFSPI openstatsware working group: GSWEP4R workshops, openpharma packages, HTA-R workstream (1 source)
- [[R Consortium pharma-skills — BioPharma Agent Skills]] — R Consortium GitHub repository of LLM agent skills for pharma; current skill: group sequential design for survival endpoints (OS, PFS, DFS) (1 source)

---

## Concepts

Statistical concepts, methods, estimands, and analytical frameworks.

- [[LLM Wiki Pattern]] — three-layer architecture (raw sources → wiki → schema) where an LLM maintains a compounding knowledge base instead of performing query-time retrieval (1 source)
- [[CDISC SDTM]] — the Study Data Tabulation Model standard for organizing clinical trial data in regulatory submissions; defines domains, variables, and controlled terminology (3 sources)
- [[CDISC ADaM]] — Analysis Data Model standard; analysis-ready datasets derived from SDTM; key dataset types (ADSL, BDS, OCCDS); traceability requirements; R implementation via {admiral} (2 sources)
- [[sdtm.oak Programming Framework]] — modular algorithm-centric approach to creating SDTM datasets in R using 8 named algorithms; replaces ad hoc dplyr/case_when chains (1 source)
- [[Analysis Results Data]] — CDISC ARS / ARDM standard for machine-readable analysis results; six ARDM principles; {cards} implementation; four-table data model; OMOP as benchmark (3 sources)
- [[Dataset-JSON]] — CDISC JSON-based transport format for SDTM/ADaM datasets; modern replacement for SAS XPT; supported by FDA (April 2025 Federal Register); used in R Consortium Pilot 5 (2 sources)
- [[GxP Validation]] — regulatory Good Practice validation framework for clinical software: GAMP 5 category system, SDLC requirements, 21 CFR Part 11, risk-based approach (3 sources)
- [[IND Safety Reporting]] — FDA framework for expedited adverse event reporting during IND studies: 7-day/15-day reports, causality assessment, aggregate safety review under 21 CFR 312.32 (1 source)
- [[Group Sequential Design]] — adaptive trial design with pre-specified interim analyses; alpha-spending functions (O'Brien-Fleming, Pocock, Kim-DeMets) control familywise error rate; applied to survival and binary endpoints (1 source)
- [[Shiny App Testing]] — three-tier testing taxonomy for R Shiny applications: unit tests, server function tests, and snapshot/E2E tests via shinytest2; GxP evidence layers; robust test patterns (3 sources)

---

## Entities

People, R packages, software tools, datasets, and organizations.

### People
- [[Andrej Karpathy]] — AI researcher; proposed the LLM Wiki Pattern (1 source)
- [[Rammprasad Ganapathy]] — Principal Data Scientist at Roche; creator of the sdtm.oak R package (1 source)
- [[Jenny Bryan]] — Software engineer at Posit; author of Happy Git and GitHub for the useR; creator of {usethis} and {reprex} (1 source)

### R Packages — CDISC Pipeline
- [[sdtm.oak R Package]] — R package for creating CDISC SDTM datasets from raw EDC data; part of Pharmaverse; production-ready at Roche (1 source)
- [[admiral R Package]] — Pharmaverse ADaM-building package; TA extensions for oncology, immunology, vaccines; four design principles (3 sources)
- [[cards R Package]] — Core ARD creation: descriptive statistics (N, mean, SD, percentages, CIs) as CDISC ARS-compliant structured objects (2 sources)
- [[cardx R Package]] — Extended ARDs: t-tests, MMRM, Cox PH, regression, survey stats; builds on {cards} (1 source)

### R Packages — TLG Production
- [[tern R Package]] — NEST stack analysis functions: g_km, g_forest, g_waterfall, summarize_coxreg; works with {rtables} layout engine (2 sources)
- [[rtables R Package]] — hierarchical table layout engine; layout API (lyt, analyze, summarize_row_groups); cell values separate from display (2 sources)
- [[chevron R Package]] — Pre-built TLG catalog as S4 objects; preprocess/main/postprocess slots; run() interface; GDS naming convention (2 sources)
- [[teal R Package]] — Interactive Shiny exploration layer built on {tern}; module ecosystem; GxP deployment support (2 sources)
- [[gtsummary R Package]] — publication-ready summary tables: tbl_summary(), tbl_regression(), inline_text(); ARD integration; output to gt/flextable/kableExtra (2 sources)
- [[patchwork R Package]] — ggplot2 multi-panel composition: `+`/`/`/`|` operators; `plot_layout()` for sizing; `plot_annotation()` for titles (1 source)

### R Packages — Validation / Testing
- [[riskmetric R Package]] — R package computing standardized quality/risk metrics for any R package; used for risk-tiered validation decisions in pharmaceutical settings (1 source)
- [[shinytest2 R Package]] — end-to-end snapshot testing for R Shiny apps; AppDriver class; robust data-testid pattern; GxP PQ evidence (2 sources)
- [[covr R Package]] — line-by-line test coverage for R packages; report(), zero_coverage(), # nocov; GitHub Actions integration; GxP dossier evidence (1 source)
- [[r4sub R Package]] — submission readiness meta-package: SCI scoring, FMEA risk assessment, traceability engine (1 source)
- [[datasetjson R Package]] — Atorus Research R package for creating, reading, and writing CDISC Dataset-JSON v1.1 files; primary tool in R Consortium Pilot 5 (1 source)

### Organizations
- [[Pharmaverse]] — open-source R package ecosystem for end-to-end CDISC-compliant clinical reporting (raw EDC → SDTM → ADaM → TLGs); 10+ core packages (4 sources)
- [[CAMIS Working Group]] — PHUSE/PSI/ASA/IASCT cross-industry initiative comparing 66+ statistical method implementations across R, SAS, and Python to explain regulatory-relevant discrepancies (2 sources)
- [[openstatsware]] — ASA BIOP and PSI/EFSPI statistical software engineering working group; produces GSWEP4R workshops, openpharma packages, HTA-R workstream (1 source)
- [[R Validation Hub]] — cross-industry pharmaR collaboration providing `{riskmetric}`, `{riskassessment}`, and a white paper on risk-based R package validation for regulated environments (1 source)
- [[R Consortium Submissions Working Group]] — working group demonstrating R-based FDA submissions via public Pilots 1–7; Pilot 5 uses Dataset-JSON; Pilots 6 & 7 launched 2026 (2 sources)

---

## Topics

Broad syntheses spanning multiple concepts and sources.

- [[R Package Validation in Regulated Environments]] — how pharma/biotech validate R packages, Shiny apps, and R infrastructure for FDA/EMA GxP compliance; three-layer stack (environment → packages → application SDLC); Shiny testing framework (9 sources)
- [[Regulatory Data Submission Standards]] — FDA technical standards for clinical trial data in drug applications: SDTM, ADaM, transport formats (XPT→Dataset-JSON), define.xml, r4sub submission readiness, Paradigm Health real-time review (7 sources)
- [[Cross-Language Statistical Implementations (R, SAS, Python)]] — how statistical methods yield different numerical results across languages; CAMIS as the authoritative reference; regulatory implications for dual programming and ADRG documentation (2 sources)
- [[TLG Production Pipeline in R]] — full CDISC pipeline from EDC to submission-ready TLGs; NEST stack (rtables/tern/chevron/teal) vs. ARD stack (cards/cardx/gtsummary); package roles and relationships (7 sources)
- [[ARD-Based Clinical Reporting]] — workflow architecture separating computation (ARD objects) from presentation; CDISC ARS standard; {cards}/{cardx}/{gtsummary}; contrast with traditional TLG approach; medical writing automation (3 sources)
- [[Shiny App Testing in Pharma]] — GxP testing strategy for R Shiny apps: four-layer evidence table; Emily Yates three-pillar framework; Appsilon DoD approach; robust shinytest2 patterns; {covr} coverage (3 sources)

---

## Schema & Meta

- `CLAUDE.md` — operating schema: directory layout, workflows, conventions, log/index formats
- `wiki/log.md` — append-only activity log (grep: `grep "^## \[" wiki/log.md`)
- `wiki/templates/source-summary.md` — template for source pages
- `wiki/templates/concept-page.md` — template for concept pages
- `wiki/templates/entity-page.md` — template for entity pages
- `wiki/templates/topic-page.md` — template for topic pages
