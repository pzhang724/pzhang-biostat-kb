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
