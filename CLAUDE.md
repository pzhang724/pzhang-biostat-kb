# CLAUDE.md — pzhang-biostat-kb Operating Schema

This is the schema for `pzhang-biostat-kb`, a personal biostatistics knowledge base using the **LLM Wiki pattern**. You (Claude) maintain the `wiki/` directory entirely. The human curates `raw/` sources and directs analysis. You never modify `raw/`.

---

## Repository Layout

```
pzhang-biostat-kb/
├── CLAUDE.md                    # This file — operating schema
├── raw/
│   ├── assets/                  # Downloaded images and attachments
│   └── sources/                 # Raw source files (markdown, clipped articles, notes)
└── wiki/
    ├── index.md                 # Full content catalog — update on every ingest
    ├── log.md                   # Append-only activity log
    ├── sources/                 # One summary page per raw source
    ├── concepts/                # Statistical concepts, methods, estimands, frameworks
    ├── entities/                # People, R packages, software, datasets, organizations
    ├── topics/                  # Broader topic syntheses spanning multiple concepts
    └── templates/               # Page templates (reference only — do not modify)
```

---

## Domain Context

This is a **biostatistics** knowledge base. Primary subject areas:

- Statistical methods: survival analysis, mixed models, Bayesian inference, causal inference, multiple testing, missing data, adaptive designs
- Biostatistical software: R packages (survival, lme4, brms, rstan, etc.), SAS, Stan
- Study design: clinical trials, RCTs, observational studies, platform trials, estimands (ICH E9 R1)
- Applied domains: oncology, epidemiology, genomics, pharmacokinetics
- Key researchers, textbooks, and landmark papers in biostatistics

When writing pages, emphasize: **assumptions, estimands, software implementations, and connections to applied contexts.** Note when methods require specific data structures or sample sizes.

---

## Page Conventions

### YAML Frontmatter

Every wiki page must have frontmatter:

```yaml
---
title: "Page Title"
type: source | concept | entity | topic
tags: [tag1, tag2]
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: 1          # count of raw sources that have informed this page
---
```

### Cross-References

- Use Obsidian wiki-links: `[[Page Title]]`
- For section anchors: `[[Cox Proportional Hazards#Assumptions]]`
- Every page must contain at least one outbound link to another wiki page
- When you create a new page, check existing pages that should link back to it and add those links

### File Naming

- `wiki/sources/` — kebab-case matching the source title, e.g. `cox-1972-regression-models.md`
- `wiki/concepts/` — kebab-case concept name, e.g. `cox-proportional-hazards.md`
- `wiki/entities/` — kebab-case, e.g. `survival-r-package.md`, `david-cox.md`
- `wiki/topics/` — kebab-case, e.g. `time-to-event-analysis.md`

---

## Workflows

### Ingest Workflow

When told to ingest a source (e.g. "ingest raw/sources/foo.md"):

1. **Read** the raw source from `raw/sources/`
2. **Discuss** key takeaways with the human (skip only if told to batch-ingest)
3. **Create** a source summary page in `wiki/sources/` using `wiki/templates/source-summary.md`
4. **Create or update** concept pages for the main statistical methods covered
5. **Create or update** entity pages for key people, packages, datasets mentioned
6. **Update** `wiki/index.md` — add/revise entries for every new or updated page
7. **Append** a log entry to `wiki/log.md` (see Log Format below)

A single source typically touches 5–15 wiki pages.

### Query Workflow

When the human asks a question about the knowledge base:

1. Read `wiki/index.md` to identify relevant pages
2. Read those pages in full
3. Synthesize an answer with wiki citations (`[[Page Title]]`) and raw source references
4. If the answer is substantial and reusable, offer to file it as a new topic or concept page

### Lint Workflow

When told to "lint the wiki":

1. Read all pages listed in `wiki/index.md`
2. Check for:
   - Contradictions between pages (flag both pages)
   - Claims superseded by newer sources
   - Orphan pages (no inbound links from any other page)
   - Concepts mentioned inline but lacking their own page
   - Missing cross-references between clearly related pages
   - Data gaps that a targeted web search could fill
3. Report findings as a numbered checklist
4. Fix each item only after human approval (unless trivially mechanical, e.g. adding a missing link)

---

## Log Format

Each entry begins with `## [YYYY-MM-DD] operation | title` so the log is grep-parseable:

```bash
grep "^## \[" wiki/log.md | tail -10   # last 10 entries
grep "ingest" wiki/log.md              # all ingests
```

**Supported operations:** `setup`, `ingest`, `query`, `lint`, `update`

**Entry structure:**
```markdown
## [YYYY-MM-DD] operation | Title

- Source: raw/sources/filename.md          (for ingests)
- Pages created: wiki/sources/x.md, wiki/concepts/y.md
- Pages updated: wiki/index.md, wiki/concepts/z.md
- Notes: any notable observations, contradictions found, questions raised
```

---

## Index Format

`wiki/index.md` is organized into sections. Each line:
```
- [[Page Title]] — one-sentence description (N sources)
```

Sections: **Sources**, **Concepts**, **Entities**, **Topics**

Update the index on every ingest. The LLM reads the index first when answering queries to find relevant pages before drilling into them.

---

## Output Formats for Query Answers

Match format to question type:
- Factual / lookup → prose paragraph with inline citations
- Comparison → markdown table
- Method overview → structured page using concept template
- "What should I read?" → annotated list from Sources section of index
- Analysis / synthesis → topic page draft for human review

---

## Notes

- This wiki is **your (Claude's) artifact**. Keep it internally consistent. When you update a page, check that downstream links still make sense.
- The human owns `raw/` and `CLAUDE.md`. Propose changes to `CLAUDE.md` as suggestions; do not edit it unilaterally.
- Prefer depth over breadth on concept pages. A thorough page on one method is more valuable than thin stubs on five.
- When in doubt about page scope, ask the human before creating.
