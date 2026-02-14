---
name: superpowers-executing-plans
description: Execute implementation plans in batches with review checkpoints between each batch
domain: "implementation"
confidence: "high"
source: "manual"
---

## Context

Use when you have a written implementation plan to execute. Load the plan, review it critically, execute tasks in batches, and report for review between batches.

## Patterns

1. **Load and review the plan** — Read the full plan before starting; flag any issues
2. **Execute in batches** — Group related tasks, execute them, then pause for review
3. **Human checkpoints** — Report progress between batches; get approval before continuing
4. **Verify each task** — Run the verification step for every task before moving on
5. **Track completion** — Mark tasks as done in the plan as you go
6. **Use git worktrees** — Work in an isolated worktree when possible

## Examples

**Workflow:**
1. Load the plan file
2. Execute tasks 1–3 (related setup tasks)
3. Report: "Tasks 1–3 complete. Tests passing. Ready for tasks 4–6?"
4. Get approval, continue

## Anti-Patterns

- Executing the entire plan without checkpoints
- Skipping verification steps to "save time"
- Not using worktrees for isolation
- Modifying the plan without discussing changes first
