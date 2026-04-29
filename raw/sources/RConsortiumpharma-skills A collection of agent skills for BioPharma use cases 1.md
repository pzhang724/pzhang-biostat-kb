---
title: "RConsortium/pharma-skills: A collection of agent skills for BioPharma use cases"
source: "https://github.com/RConsortium/pharma-skills/tree/main"
author:
published:
created: 2026-04-29
description: "A collection of agent skills for BioPharma use cases - RConsortium/pharma-skills"
tags:
  - "clippings"
---
## Pharma Skills

A collection of agent skills for pharmaceutical R&D.

## Skills

| Skill | Description |
| --- | --- |
| [group-sequential-design](https://github.com/RConsortium/pharma-skills/blob/main/group-sequential-design) | Design group sequential clinical trials for survival endpoints (OS, PFS, DFS) with interim analyses, spending functions, multiplicity, and event/enrollment prediction |

## Usage

**Option 1: Conversational / CLI** Ask your agent to directly enable a skill from this repo:

> enable "group-sequential-design" skill from [https://github.com/RConsortium/pharma\_skills](https://github.com/RConsortium/pharma_skills)

**Option 2: Local IDE (Cursor, Windsurf, Copilot, etc.)**

1. Clone this repository locally or as a git submodule.
2. Symlink the skill you want into your project, or manually reference it in your configuration files (like `.cursorrules` or `llms.txt`): `Please refer to /path/to/pharma_skills/group-sequential-design/SKILL.md for the trial design workflow.`

## Contributing

### New Skills

Contributions of new skills are welcome. Each skill should:

1. Live in its own folder at the repo root
2. Include a `SKILL.md` with frontmatter (`name`, `description`) and instructions
3. Include a `README.md` describing what the skill does, requirements, and usage
4. Include an MIT `LICENSE`
5. Follow the [Agent Skill Development Lifecycle](https://github.com/RConsortium/pharma-skills/blob/main/LIFECYCLE.md)

### New Benchmark data

You can add new benchmark data by creating new github issues following the `benchmark` templates.

### Evaluate Benchmark data

If you're interested in contributing to the skill evaluation using your Claude Code account, following this [video](https://github.com/user-attachments/assets/05d24707-36b8-49fc-86ea-beb6365e288e) to set it up.

## License

All skills in this repository are required to be licensed under the MIT License to ensure maximum permissiveness and rapid adoption within pharmaceutical research.