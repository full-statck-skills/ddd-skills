# CLAUDE.md

## Project Overview

`ddd-skills` is a plugin collection of **16 Agent Skills** for Domain-Driven Design architecture — part of the [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem by PartMe.AI. Each skill is a self-contained `SKILL.md` file that AI agents load on-demand.

- **Install**: `npx skills add full-statck-skills/ddd-skills`
- **License**: Apache-2.0

## Directory Structure

```
ddd-skills/
├── .claude-plugin/plugin.json    # Plugin metadata (name, version, skill registry)
├── README.md / README.zh-CN.md   # Bilingual project documentation
└── skills/
    └── <skill-name>/             # Each skill is a directory
        ├── SKILL.md              # YAML frontmatter + markdown body
        ├── examples/             # Example code and templates
        ├── references/           # Reference docs and diagrams
        └── scripts/              # Optional build/utility scripts
```

## Skills (16)

| # | Skill | Focus |
|---|-------|-------|
| 1 | `ddd-architecture-selector` | Decision guide — choose among 5 DDD architectures |
| 2 | `ddd-architecture-layered` | DDD 4-layer (Interface→Application→Domain→Infrastructure) |
| 3 | `ddd-architecture-onion` | Onion Architecture (Jeffrey Palermo) |
| 4 | `ddd-architecture-hexagonal` | Ports & Adapters (Alistair Cockburn) |
| 5 | `ddd-architecture-clean` | Clean Architecture (Robert C. Martin) |
| 6 | `ddd-architecture-cola` | COLA v5 / Diamond Architecture (Alibaba) |
| 7 | `ddd-architecture-awesome` | Comprehensive DDD concepts & patterns reference |
| 8 | `ddd-domain-designer` | Domain modeling — event-storming→aggregate→bounded context |
| 9 | `ddd-event-storming` | Event Storming workshop facilitation (6-step) |
| 10 | `ddd-api-designer` | REST API from domain model — CQRS, DTO chain, BFF |
| 11 | `ddd-cqrs-architecture` | CQRS — L1/L2/L3 levels, Event Sourcing |
| 12 | `ddd-code-reviewer` | DDD anti-pattern detection & architecture compliance |
| 13 | `ddd-testing-strategist` | Aggregate/domain/repository/application layer testing |
| 14 | `ddd-architecture-doc` | C4 model diagrams, ADR, PlantUML generation |
| 15 | `ddd-architecture-evaluator` | DDD maturity assessment (5-level model) |
| 16 | `ddd-devops-integration` | CI/CD + ArchUnit validation, multi-module builds |

## SKILL.md Authoring Conventions

Each `SKILL.md` follows this pattern:

```yaml
---
name: ddd-skill-name           # kebab-case, matches directory name
description: <one-line summary> # SHOULD include "Use when user asks about ..." triggers
license: Apache-2.0
---
```

Body sections (in order):
1. **H1 heading** — Skill title (English or bilingual)
2. **Workflow** — Numbered step-by-step process
3. **When to Use** — Table: ALWAYS use column (trigger keywords) vs Skip column (exclusions)
4. **Detailed guidance** — Architecture diagrams, code examples, templates, checklists
5. **Related skills** — Cross-references to other skills in the collection

- Lines per SKILL.md: ~170–510 (most ~200)
- Use Chinese for domain terminology when skill targets Chinese-speaking audience
- Skills reference each other (e.g., domain-designer references event-storming)

## Key Files

- `.claude-plugin/plugin.json` — Add new skills to the `skills` array here
- `README.md` / `README.zh-CN.md` — Update the skills table when adding/removing skills
- `skills/<name>/SKILL.md` — The actual skill content loaded by agents
