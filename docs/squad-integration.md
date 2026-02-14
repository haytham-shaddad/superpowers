# Squad AI Team Integration

Superpowers skills are available for use with [Squad](https://github.com/bradygaster/squad) AI agent teams — in both GitHub Copilot in VS Code and CLI.

## Overview

Superpowers provides a library of composable development workflow skills covering brainstorming, planning, TDD, debugging, code review, and more. These skills can be used by Squad agents as `.ai-team/skills/` entries, following Squad's skill format.

## How It Works

### Skills as Squad Skills

Superpowers skills are provided in two formats:

1. **Original format** (`skills/` directory) — Full skill files with Superpowers frontmatter (`name`, `description`). These are the authoritative, detailed versions used by Claude Code, Codex, and OpenCode.

2. **Squad format** (`.ai-team/skills/` directory) — Squad-compatible skill files with full Squad frontmatter (`name`, `description`, `domain`, `confidence`, `source`).

### Using with Squad

When Squad is initialized in a project that includes Superpowers:

1. Squad agents automatically discover skills in `.ai-team/skills/`
2. Superpowers skills appear with the `superpowers-` prefix (e.g., `superpowers-brainstorming`)
3. Agents read relevant skills before working on tasks
4. Skills are shared across all Squad team members

### Available Skills

| Squad Skill Name | Domain | Description |
|-----------------|--------|-------------|
| `superpowers-brainstorming` | planning | Collaborative design refinement before creative work |
| `superpowers-writing-plans` | planning | Comprehensive implementation plans with bite-sized tasks |
| `superpowers-executing-plans` | implementation | Batch execution with review checkpoints |
| `superpowers-subagent-driven-development` | implementation | Fresh agent per task with two-stage review |
| `superpowers-test-driven-development` | testing | RED-GREEN-REFACTOR cycle |
| `superpowers-systematic-debugging` | debugging | 4-phase root cause analysis |
| `superpowers-verification` | quality | Evidence-based completion verification |
| `superpowers-code-review-request` | quality | Pre-review compliance checklist |
| `superpowers-code-review-receive` | quality | Technical evaluation of review feedback |
| `superpowers-git-worktrees` | workflow | Isolated workspaces for feature development |
| `superpowers-finishing-branch` | workflow | Guided branch completion and cleanup |
| `superpowers-parallel-agents` | implementation | Concurrent agent dispatch for independent tasks |
| `superpowers-writing-skills` | meta | Creating new skills following best practices |

## Setup

### Option 1: Clone Superpowers into your project

```bash
# From your project root
git clone https://github.com/obra/superpowers.git .superpowers

# Copy Squad-compatible skills
cp -r .superpowers/.ai-team/skills/* .ai-team/skills/
```

### Option 2: Add as a git submodule

```bash
git submodule add https://github.com/obra/superpowers.git .superpowers
cp -r .superpowers/.ai-team/skills/* .ai-team/skills/
```

### Option 3: Manual copy

Copy the `.ai-team/skills/superpowers-*/` directories from this repository into your project's `.ai-team/skills/` directory.

## Using Without Squad

The skills in `.ai-team/skills/` are standard markdown files. They work with any AI coding agent that reads markdown instructions:

- **GitHub Copilot** — Skills are referenced in `.github/copilot-instructions.md`
- **Claude Code** — Use the plugin system (see main README)
- **Codex** — See `.codex/INSTALL.md`
- **OpenCode** — See `.opencode/INSTALL.md`
- **Manual use** — Read the skill files directly as development process guides

## Skill Confidence Levels

All Superpowers skills are shipped with `confidence: high` since they are battle-tested patterns from the Superpowers project. As your team uses them, confidence is maintained by Squad's standard lifecycle.

## Creating Custom Skills

Use the `superpowers-writing-skills` skill to create new skills. New skills should follow the Squad SKILL.md format:

```yaml
---
name: "my-custom-skill"
description: "What this skill teaches agents"
domain: "e.g., testing, planning, workflow"
confidence: "low"
source: "earned"
---

## Context
When and why this skill applies

## Patterns
Specific patterns and approaches

## Examples
Code examples or references

## Anti-Patterns
What to avoid
```
