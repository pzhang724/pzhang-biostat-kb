# pzhang-biostat-kb

A personal biostatistics knowledge base built on the [LLM Wiki pattern](https://gist.github.com/karpathy/b54c9c9ab43bde8b7b4e3b4c8a6c0f0e) — an LLM (Claude) maintains a structured `wiki/` from raw clipped sources, replacing query-time RAG with a compounding, human-readable knowledge graph.

## Using this vault in Obsidian

[Obsidian](https://obsidian.md) is a free desktop app that renders this repo as a linked knowledge base.

1. **Download Obsidian** from https://obsidian.md and install it.
2. **Clone this repo** to your local machine:
   ```bash
   git clone https://github.com/pzhang724/pzhang-biostat-kb.git
   ```
3. **Open as a vault**: launch Obsidian → *Open folder as vault* → select the cloned folder.
4. **Start exploring**: open `wiki/index.md` as your entry point — every page is linked from there.

> **Tip**: Install the [Dataview](https://github.com/blacksmithgu/obsidian-dataview) community plugin for richer queries across frontmatter.

## Repository layout

```
raw/sources/    ← clipped articles, transcripts, FDA guidance (human-curated)
wiki/           ← structured knowledge pages (LLM-maintained)
  index.md      ← master catalog — start here
  log.md        ← append-only ingest history
  sources/      ← one summary page per raw source
  concepts/     ← statistical methods, estimands, frameworks
  entities/     ← people, R packages, organizations
  topics/       ← broad syntheses spanning multiple concepts
CLAUDE.md       ← operating schema for the LLM wiki workflow
```

## Domain

Biostatistics, clinical trials, regulatory submissions (FDA/CDISC), and the R/Python ecosystem for pharmaceutical statistics.
