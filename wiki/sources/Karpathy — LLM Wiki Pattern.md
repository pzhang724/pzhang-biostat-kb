---
title: "Karpathy — LLM Wiki Pattern"
aliases: ["Karpathy — LLM Wiki Pattern"]
type: source
tags: [knowledge-management, llm-tooling, meta, obsidian]
created: 2026-04-27
updated: 2026-04-27
sources: 1
---

# Karpathy — LLM Wiki Pattern

**Raw file**: `raw/sources/karpathy-llm-wiki.md`  
**Author(s)**: Andrej Karpathy  
**Year**: 2026  
**Type**: blog-post (GitHub Gist)  
**Venue**: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

## Summary

Karpathy proposes replacing RAG-style knowledge systems with a **persistent, LLM-maintained wiki**: instead of retrieving raw document chunks at query time, the LLM incrementally builds and updates a structured set of interlinked markdown pages. Knowledge accumulates rather than being re-derived on every question. The human curates sources and asks questions; the LLM handles all the bookkeeping.

## Key Points

- The fundamental shift: from **retrieval** (RAG) to **compilation + maintenance** (LLM Wiki). The wiki is built once and kept current, not re-derived on every query.
- Three-layer architecture: **raw sources** (immutable) → **wiki** (LLM-owned markdown) → **schema** (CLAUDE.md / AGENTS.md configuration). See [[LLM Wiki Pattern]].
- A single ingest typically touches 10–15 wiki pages: summary, concept updates, entity updates, index, log.
- Good query answers should be **filed back** as new pages — explorations compound just like ingested sources.
- `index.md` (content catalog) + `log.md` (chronological record with grep-parseable headers) are the two navigation files.
- **Obsidian as the IDE**, the LLM as the programmer, the wiki as the codebase.
- Inspired by Vannevar Bush's **Memex** (1945): private, curated, associative knowledge store.

## Methods / Concepts Covered

- [[LLM Wiki Pattern]] — the core architectural pattern described throughout
- RAG (Retrieval-Augmented Generation) — discussed as the alternative/predecessor approach
- Obsidian — recommended as the browsing interface

## Notable Quotes

> "The wiki is a persistent, compounding artifact. The cross-references are already there. The contradictions have already been flagged."

> "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase."

> "LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass."

> "The idea is related in spirit to Vannevar Bush's Memex (1945)."

## Connections

- This source is the **founding document** for the architecture of this entire knowledge base
- See `CLAUDE.md` for the biostatistics-specific instantiation of this pattern
- Contrast with: NotebookLM, ChatGPT file uploads, standard RAG systems

## Questions Raised

- At what scale does the index file stop being sufficient and require vector search (qmd or similar)?
- How to handle sources with heavy figure/table content that LLMs can't read in one pass?
- What is the right cadence for lint passes as the wiki grows?
