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
