# Squad AI Team Integration Plan

**Date:** 2026-02-14
**Status:** Implementation Complete

## Overview

Make Superpowers skills usable with Squad AI Team (@bradygaster/squad) as Squad-compatible skills, working in both GitHub Copilot in VS Code and CLI.

## Goals

1. Convert Superpowers skills to Squad SKILL.md format (with `domain`, `confidence`, `source` fields)
2. Provide `.github/copilot-instructions.md` for GitHub Copilot integration
3. Document integration setup for Squad users
4. Move Claude Code and Jesse-specific instructions to a labeled section
5. Maintain backward compatibility with Claude Code, Codex, and OpenCode

## What Was Done

### Task 1: Squad-Compatible Skills (`.ai-team/skills/`)

Created 13 Squad-formatted skill files in `.ai-team/skills/superpowers-*/SKILL.md`:

- `superpowers-brainstorming` — planning domain
- `superpowers-writing-plans` — planning domain
- `superpowers-executing-plans` — implementation domain
- `superpowers-subagent-driven-development` — implementation domain
- `superpowers-test-driven-development` — testing domain
- `superpowers-systematic-debugging` — debugging domain
- `superpowers-verification` — quality domain
- `superpowers-code-review-request` — quality domain
- `superpowers-code-review-receive` — quality domain
- `superpowers-git-worktrees` — workflow domain
- `superpowers-finishing-branch` — workflow domain
- `superpowers-parallel-agents` — implementation domain
- `superpowers-writing-skills` — meta domain

Each skill uses Squad's frontmatter format and references the full Superpowers skill for detailed content.

### Task 2: GitHub Copilot Instructions

Created `.github/copilot-instructions.md` with:
- Skills table for quick reference
- Usage instructions for Squad and standalone Copilot
- Core principles
- Plan artifact conventions

### Task 3: Integration Documentation

Created `docs/squad-integration.md` with:
- Setup options (clone, submodule, manual copy)
- Skills catalog with domains
- Usage without Squad (standalone Copilot, manual use)
- Custom skill creation guide

### Task 4: README Updates

- Added Squad AI Team as the first installation option
- Moved Claude Code and Jesse-specific instructions to a labeled section at the bottom
- Maintained all existing platform documentation
- Updated agent-neutral language in the main description

## Decisions

- **Skills are summaries, not copies** — Squad skills reference the full Superpowers skills for detail. This avoids content duplication and keeps maintenance simple.
- **All skills shipped as `confidence: high`** — Superpowers skills are battle-tested; no need for the low→medium→high lifecycle.
- **Prefixed with `superpowers-`** — Prevents name collisions with other Squad skills or plugins.
- **Backward compatible** — All existing Claude Code, Codex, and OpenCode installations continue to work unchanged.
