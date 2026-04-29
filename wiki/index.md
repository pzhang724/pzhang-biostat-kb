---
title: "Wiki Index"
type: meta
updated: 2026-04-29
total_sources: 14
total_pages: 34
---

# Wiki Index

Master catalog of all pages in this knowledge base. Updated on every ingest.

**Quick stats**: 14 sources ingested · 34 wiki pages · last updated 2026-04-29

**Navigation tip**: Read this file first when answering a query. Find relevant pages, then drill in.

---

## Sources

Source summary pages — one per raw document ingested.

- [[Karpathy — LLM Wiki Pattern]] — Andrej Karpathy's gist describing the LLM Wiki architecture: persistent wiki maintained by LLM, replacing RAG for personal knowledge bases (1 source)
- [[SDTM programming in R using {sdtm.oak} package]] — R in Pharma 2026 workshop by Rammprasad Ganapathy (Roche) covering all 8 sdtm.oak algorithms with worked examples across CM, VS, AE, DM domains (1 source)
- [[Sponsor Responsibilities — IND Safety Reporting]] — FDA guidance on IND expedited safety reporting (7-day/15-day reports), causality assessment, and aggregate data provisions under 21 CFR 312.32 (1 source)
- [[FDA Study Data Technical Conformance Guide]] — FDA technical specifications for electronic study data submissions: SDTM, ADaM, define.xml, file formats, and Pinnacle 21 validation requirements (1 source)
- [[FDA Guidance — Oncology Radiopharmaceutical Dosage Optimization]] — FDA guidance for sponsors identifying optimized dosage (administered activity + schedule) for radiopharmaceutical therapies in oncology clinical development (1 source)
- [[Breaking Free from the XPT — Dataset-JSON as Regulatory Transport]] — PHUSE paper arguing for Dataset-JSON v1.1 as XPT replacement; documents R Consortium Submission Pilot 5 (full R pipeline, all datasets as Dataset-JSON, submitted Fall 2025) (1 source)
- [[pharmaR — The R Validation Hub]] — overview of the R Validation Hub: `{riskmetric}`, `{riskassessment}`, risk-based white paper, and regulatory R repository initiative (1 source)
- [[GxP Validation in Clinical Software Development (Appsilon)]] — practical overview of all GxP domains (CGMP, GLP, GCP, GAMP) and seven good software engineering practice areas for FDA/EMA submission software (1 source)
- [[Emily Yates — Validating GxP-Compliant R Shiny Apps]] — R/Pharma 2024 talk by Emily Yates (Formation Bio): three-pillar GxP validation framework for clinical R Shiny apps — validated environment, risk-based packages, GAMP 5-aligned SDLC (1 source)
- [[Posit — Validated R Package Strategy]] — Posit documentation: creating a controlled, audit-ready internal R package repository using Posit Package Manager and `{renv}` for regulated environments (1 source)
- [[GSWEP4R Workshop — R Package Engineering Workflow]] — openstatsware workshop slide deck: professional vs. anti-pattern R package development workflows; SDLC rationale grounded in empirical cost/error data (1 source)
- [[CAMIS — Cross-Language Statistical Method Comparisons (PHUSE)]] — PHUSE DVOST living reference repository: 60+ statistical methods compared across R, SAS, and Python with discrepancy explanations; regulatory motivation (1 source)
- [[openstatsware — Statistical Software Engineering Working Group]] — overview of the ASA/PSI/EFSPI openstatsware working group: GSWEP4R workshops, openpharma packages, HTA-R workstream (1 source)
- [[R Consortium pharma-skills — BioPharma Agent Skills]] — R Consortium GitHub repository of LLM agent skills for pharma; current skill: group sequential design for survival endpoints (OS, PFS, DFS) (1 source)

---

## Concepts

Statistical concepts, methods, estimands, and analytical frameworks.

- [[LLM Wiki Pattern]] — three-layer architecture (raw sources → wiki → schema) where an LLM maintains a compounding knowledge base instead of performing query-time retrieval (1 source)
- [[CDISC SDTM]] — the Study Data Tabulation Model standard for organizing clinical trial data in regulatory submissions; defines domains, variables, and controlled terminology (3 sources)
- [[sdtm.oak Programming Framework]] — modular algorithm-centric approach to creating SDTM datasets in R using 8 named algorithms; replaces ad hoc dplyr/case_when chains (1 source)
- [[Dataset-JSON]] — CDISC JSON-based transport format for SDTM/ADaM datasets; modern replacement for SAS XPT; supported by FDA (April 2025 Federal Register); used in R Consortium Pilot 5 (2 sources)
- [[GxP Validation]] — regulatory Good Practice validation framework for clinical software: GAMP 5 category system, SDLC requirements, 21 CFR Part 11, risk-based approach (3 sources)
- [[IND Safety Reporting]] — FDA framework for expedited adverse event reporting during IND studies: 7-day/15-day reports, causality assessment, aggregate safety review under 21 CFR 312.32 (1 source)
- [[Group Sequential Design]] — adaptive trial design with pre-specified interim analyses; alpha-spending functions (O'Brien-Fleming, Pocock, Kim-DeMets) control familywise error rate; applied to survival and binary endpoints (1 source)

---

## Entities

People, R packages, software tools, datasets, and organizations.

- [[Andrej Karpathy]] — AI researcher; proposed the LLM Wiki Pattern (1 source)
- [[sdtm.oak R Package]] — R package for creating CDISC SDTM datasets from raw EDC data; part of Pharmaverse; production-ready at Roche (1 source)
- [[Pharmaverse]] — open-source R package ecosystem for end-to-end CDISC-compliant clinical reporting (raw EDC → SDTM → ADaM → TLGs) (2 sources)
- [[Rammprasad Ganapathy]] — Principal Data Scientist at Roche; creator of the sdtm.oak R package (1 source)
- [[CAMIS Working Group]] — PHUSE/PSI/ASA/IASCT cross-industry initiative comparing 60+ statistical method implementations across R, SAS, and Python to explain regulatory-relevant discrepancies (1 source)
- [[openstatsware]] — ASA BIOP and PSI/EFSPI statistical software engineering working group; produces GSWEP4R workshops, openpharma packages, HTA-R workstream (1 source)
- [[R Validation Hub]] — cross-industry pharmaR collaboration providing `{riskmetric}`, `{riskassessment}`, and a white paper on risk-based R package validation for regulated environments (1 source)
- [[riskmetric R Package]] — R package computing standardized quality/risk metrics for any R package; used for risk-tiered validation decisions in pharmaceutical settings (1 source)
- [[datasetjson R Package]] — Atorus Research R package for creating, reading, and writing CDISC Dataset-JSON v1.1 files; primary tool in R Consortium Pilot 5 (1 source)
- [[R Consortium Submissions Working Group]] — working group demonstrating R-based FDA submissions via public Pilots 1–5; Pilot 5 uses Dataset-JSON for all datasets (1 source)

---

## Topics

Broad syntheses spanning multiple concepts and sources.

- [[R Package Validation in Regulated Environments]] — how pharma/biotech validate R packages, Shiny apps, and R infrastructure for FDA/EMA GxP compliance; three-layer stack (environment → packages → application SDLC) (5 sources)
- [[Regulatory Data Submission Standards]] — FDA technical standards for clinical trial data in drug applications: SDTM, ADaM, transport formats (XPT→Dataset-JSON), define.xml, safety reporting obligations (4 sources)
- [[Cross-Language Statistical Implementations (R, SAS, Python)]] — how statistical methods yield different numerical results across languages; CAMIS as the authoritative reference; regulatory implications for dual programming and ADRG documentation (1 source)

---

## Schema & Meta

- `CLAUDE.md` — operating schema: directory layout, workflows, conventions, log/index formats
- `wiki/log.md` — append-only activity log (grep: `grep "^## \[" wiki/log.md`)
- `wiki/templates/source-summary.md` — template for source pages
- `wiki/templates/concept-page.md` — template for concept pages
- `wiki/templates/entity-page.md` — template for entity pages
- `wiki/templates/topic-page.md` — template for topic pages
