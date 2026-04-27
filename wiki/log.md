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
