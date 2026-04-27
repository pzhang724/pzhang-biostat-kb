---
title: "LLM Wiki Pattern"
type: concept
tags: [knowledge-management, llm-tooling, meta, architecture]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# LLM Wiki Pattern

A knowledge management architecture where an LLM incrementally builds and maintains a persistent, interlinked wiki from curated sources — replacing query-time retrieval with a compiled, compounding knowledge artifact.

## Overview

Most LLM-document systems work like RAG: raw documents are indexed, and at query time the LLM retrieves relevant chunks and synthesizes an answer. This means the LLM is rediscovering the same knowledge from scratch on every question. Nothing accumulates.

The LLM Wiki pattern inverts this. When a new source arrives, the LLM reads it, extracts key information, and **integrates it into the existing wiki** — updating concept pages, entity pages, noting contradictions, strengthening the synthesis. By query time, the work is mostly done: the answer is a read + synthesis of maintained pages, not a cold search through raw documents.

The result is a **compounding artifact**: each source makes the wiki richer for every future query. Each query answer can itself be filed as a new page, compounding again.

## The Three Layers

| Layer | Owner | Purpose |
|-------|-------|---------|
| **Raw sources** | Human | Immutable source of truth — articles, papers, notes, clippings |
| **Wiki** | LLM | Maintained markdown pages: summaries, concept pages, entity pages, topic syntheses |
| **Schema** | Human + LLM (co-evolved) | Configuration document (CLAUDE.md) defining structure, conventions, workflows |

## Core Operations

### Ingest
Process a new source: read → discuss takeaways → write summary page → update 5–15 concept/entity pages → update index → append log entry.

### Query
Read `index.md` → read relevant pages → synthesize answer with citations → optionally file the answer as a new page.

### Lint
Periodic health check: find contradictions, orphan pages, stale claims, missing cross-references, concepts needing their own page.

## Navigation Infrastructure

- **`index.md`** — content-oriented catalog organized by category; the LLM reads this first on every query to find relevant pages before drilling in. Sufficient up to ~100 sources / hundreds of pages without embedding infrastructure.
- **`log.md`** — append-only chronological record with grep-parseable headers (`## [YYYY-MM-DD] operation | title`).

## Comparison to RAG

| Dimension | RAG | LLM Wiki |
|-----------|-----|----------|
| Knowledge location | Raw documents | Compiled wiki pages |
| Query-time work | Retrieve chunks + synthesize | Read maintained summaries + synthesize |
| Accumulation | None | Compounds with each source and query |
| Contradiction handling | None | Flagged during ingest |
| Maintenance cost (human) | Near zero | Near zero |
| Maintenance cost (LLM) | None | Done during ingest (cost amortized) |
| Infrastructure required | Embedding store, retrieval pipeline | Git repo of markdown files |

## Workflow Tooling (Recommended)

- **[[Obsidian]]** — IDE for browsing the wiki; graph view shows link structure, orphan pages, hubs
- **Obsidian Web Clipper** — browser extension to convert articles to markdown for `raw/sources/`
- **qmd** — local hybrid BM25/vector search for markdown, with CLI + MCP interface; useful at scale (>100 sources)
- **Marp** — markdown-based slide decks; Obsidian plugin available
- **Dataview** — Obsidian plugin that queries YAML frontmatter; enables dynamic tables from page metadata

## Connections

- Inspired by: Vannevar Bush's **Memex** (1945) — private, curated, associative knowledge store with trails between documents
- Contrast with: NotebookLM, ChatGPT file uploads, standard RAG
- Instantiated in this repo as described in `CLAUDE.md`

## Key References

- [[Karpathy — LLM Wiki Pattern]] — original gist; the founding document for this wiki
