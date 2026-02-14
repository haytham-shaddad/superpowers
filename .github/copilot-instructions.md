# Superpowers — Copilot Instructions

This project uses **Superpowers**, a composable skills library for AI development workflows.

## Skills System

Before starting any task, check if a relevant skill exists in `.ai-team/skills/`. Skills encode proven patterns for brainstorming, planning, TDD, debugging, code review, and more.

### Available Skills

| Skill | Domain | When to Use |
|-------|--------|-------------|
| `superpowers-brainstorming` | planning | Before any creative work — features, components, modifications |
| `superpowers-writing-plans` | planning | With a spec or requirements, before touching code |
| `superpowers-executing-plans` | implementation | With a written plan, execute in batches with checkpoints |
| `superpowers-subagent-driven-development` | implementation | Execute plans by dispatching fresh agent per task |
| `superpowers-test-driven-development` | testing | Before writing any implementation code |
| `superpowers-systematic-debugging` | debugging | Before proposing any bug fixes |
| `superpowers-verification` | quality | Before claiming work is complete |
| `superpowers-code-review-request` | quality | Before merging or requesting review |
| `superpowers-code-review-receive` | quality | When receiving review feedback |
| `superpowers-git-worktrees` | workflow | When feature work needs isolation |
| `superpowers-finishing-branch` | workflow | When implementation is complete |
| `superpowers-parallel-agents` | implementation | When 2+ independent tasks can run concurrently |
| `superpowers-writing-skills` | meta | When creating or editing skills |

### How to Use

1. Read the relevant `SKILL.md` file from `.ai-team/skills/superpowers-{name}/SKILL.md`
2. Follow the patterns described in the skill
3. For the full detailed skill content, reference `skills/{name}/SKILL.md` in the repository root

### Core Principles

- **Test-Driven Development** — Write tests first, always
- **Systematic over ad-hoc** — Process over guessing
- **Complexity reduction** — Simplicity as primary goal
- **Evidence over claims** — Verify before declaring success
- **Brainstorm before building** — Design before implementation

## Squad AI Team Integration

If this project uses [Squad](https://github.com/bradygaster/squad), Superpowers skills are available as Squad skills in `.ai-team/skills/`. They follow Squad's SKILL.md format with `domain`, `confidence`, and `source` frontmatter fields.

Squad agents should read relevant Superpowers skills before working on tasks. The skills are compatible with Squad's skill-aware routing system.

## Plans

Implementation plans should be saved to `docs/plans/` with dated filenames following the pattern:
```
docs/plans/YYYY-MM-DD-description.md
```
