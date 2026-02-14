---
name: superpowers-subagent-driven-development
description: Execute plans by dispatching fresh subagent per task with two-stage review — spec compliance then code quality
domain: "implementation"
confidence: "high"
source: "manual"
---

## Context

Use when executing implementation plans with independent tasks. Each task is dispatched to a fresh subagent (or squad member) with full context. After completion, two review stages: spec compliance, then code quality.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Fresh agent per task** — Each task gets a clean context with the plan and relevant files
2. **Full context in prompt** — Include the task, relevant code, and constraints
3. **Two-stage review:**
   - **Stage 1: Spec compliance** — Does the output match what was planned?
   - **Stage 2: Code quality** — Is the code clean, tested, and well-structured?
4. **Reject and retry** — If review fails, dispatch a new agent (not the same one)
5. **Git worktrees** — Each agent works in an isolated worktree

### Squad Integration

In a Squad context, this maps naturally to the coordinator spawning agents for each task. The Lead or Tester agent can serve as the reviewer.

## Examples

**Task dispatch:**
1. Read plan task #3 from `docs/plans/feature.md`
2. Spawn agent with task context + relevant files
3. Agent implements + tests
4. Review stage 1: Does it match the spec?
5. Review stage 2: Is the code quality good?
6. If both pass → merge. If not → new agent.

## Anti-Patterns

- Reusing the same agent context for multiple tasks
- Skipping the review stages
- Having the same agent review its own work
- Not providing full context in the dispatch prompt

## See Also

For the full skill content, see `skills/subagent-driven-development/SKILL.md` in the Superpowers repository.
