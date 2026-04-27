---
title: "Wiki Index"
type: meta
updated: 2026-04-27
total_sources: 2
total_pages: 9
---

# Wiki Index

Master catalog of all pages in this knowledge base. Updated on every ingest.

**Quick stats**: 2 sources ingested · 9 wiki pages · last updated 2026-04-27

**Navigation tip**: Read this file first when answering a query. Find relevant pages, then drill in.

---

## Sources

Source summary pages — one per raw document ingested.

- [[Karpathy — LLM Wiki Pattern]] — Andrej Karpathy's gist describing the LLM Wiki architecture: persistent wiki maintained by LLM, replacing RAG for personal knowledge bases (1 source)
- [[SDTM Programming in R using {sdtm.oak} Package]] — R in Pharma 2026 workshop by Rammprasad Ganapathy (Roche) covering all 8 sdtm.oak algorithms with worked examples across CM, VS, AE, DM domains (1 source)

---

## Concepts

Statistical concepts, methods, estimands, and analytical frameworks.

- [[LLM Wiki Pattern]] — three-layer architecture (raw sources → wiki → schema) where an LLM maintains a compounding knowledge base instead of performing query-time retrieval (1 source)
- [[CDISC SDTM]] — the Study Data Tabulation Model standard for organizing clinical trial data in regulatory submissions; defines domains, variables, and controlled terminology (1 source)
- [[sdtm.oak Programming Framework]] — modular algorithm-centric approach to creating SDTM datasets in R using 8 named algorithms; replaces ad hoc dplyr/case_when chains (1 source)

---

## Entities

People, R packages, software tools, datasets, and organizations.

- [[Andrej Karpathy]] — AI researcher; proposed the LLM Wiki Pattern (1 source)
- [[sdtm.oak R Package]] — R package for creating CDISC SDTM datasets from raw EDC data; part of Pharmaverse; production-ready at Roche (1 source)
- [[Pharmaverse]] — open-source R package ecosystem for end-to-end CDISC-compliant clinical reporting (raw EDC → SDTM → ADaM → TLGs) (1 source)
- [[Rammprasad Ganapathy]] — Principal Data Scientist at Roche; creator of the sdtm.oak R package (1 source)

---

## Topics

Broad syntheses spanning multiple concepts and sources.

*Topics will emerge as multiple related sources are ingested.*

---

## Schema & Meta

- `CLAUDE.md` — operating schema: directory layout, workflows, conventions, log/index formats
- `wiki/log.md` — append-only activity log (grep: `grep "^## \[" wiki/log.md`)
- `wiki/templates/source-summary.md` — template for source pages
- `wiki/templates/concept-page.md` — template for concept pages
- `wiki/templates/entity-page.md` — template for entity pages
- `wiki/templates/topic-page.md` — template for topic pages
