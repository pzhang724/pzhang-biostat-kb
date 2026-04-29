---
title: "R Consortium pharma-skills — BioPharma Agent Skills"
type: source
tags: [r-consortium, ai-agents, group-sequential-design, clinical-trials, llm, pharma]
created: 2026-04-29
updated: 2026-04-29
sources: 1
---

# R Consortium pharma-skills — BioPharma Agent Skills

**Raw file**: `raw/sources/RConsortiumpharma-skills A collection of agent skills for BioPharma use cases.md`  
**Author(s)**: R Consortium  
**Year**: 2025–2026  
**Type**: open-source-repository  
**Venue**: https://github.com/RConsortium/pharma-skills

## Summary

A GitHub repository of reusable LLM agent "skills" for pharmaceutical R&D use cases, released by the R Consortium. Each skill is a structured SKILL.md file that an LLM agent can load to gain domain-specific procedural knowledge. At time of clipping, one skill was available: group sequential design for survival endpoints. The repository is designed to work with conversational AI agents (Claude Code, etc.) and local IDE tools (Cursor, Windsurf, Copilot).

## Key Points

- **Available skill**: `group-sequential-design` — covers design of group sequential clinical trials for survival endpoints (OS, PFS, DFS) with interim analyses, alpha-spending functions, multiplicity, and event/enrollment prediction
- **Usage modes**: (1) conversational — ask LLM agent to enable the skill from GitHub URL; (2) local IDE — clone repo and symlink/reference SKILL.md in project config
- **MIT licensed**: all skills must be MIT licensed for maximum permissiveness
- **Benchmark system**: issues-based benchmark data for evaluating skill performance
- **Contribution model**: new skills require SKILL.md + README.md + MIT LICENSE + lifecycle document

## Methods / Concepts Covered

- [[Group Sequential Design]] — primary method covered by the first skill
- Survival endpoint trial design: OS, PFS, DFS endpoints with interim analyses

## Connections

- Method covered: [[Group Sequential Design]]
- Related entity: [[R Consortium Submissions Working Group]] (same org, different program)
- Related topic: [[Cross-Language Statistical Implementations (R, SAS, Python)]] (CAMIS also covers GSD)
- LLM Wiki context: [[LLM Wiki Pattern]] — this source exemplifies AI agents in pharma

## Questions Raised

- How will this skill library grow — who governs which skills get contributed and validated?
- Can a GSD skill be used to automate SAP-level content for interim analysis plans?
