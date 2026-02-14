---
name: "superpowers-parallel-agents"
description: "Dispatch multiple independent tasks to concurrent agents when tasks have no shared state or sequential dependencies"
domain: "implementation"
confidence: "high"
source: "manual"
---

## Context

Use when facing 2+ independent tasks that can be worked on without shared state or sequential dependencies. Investigating them sequentially wastes time when each investigation is independent.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Identify independence** — Tasks must not share state or have sequential dependencies
2. **Dispatch in parallel** — Each task gets its own agent with full context
3. **Collect results** — Wait for all agents to complete, then review
4. **Merge carefully** — Check for conflicts when combining parallel work

### Squad Integration

In a Squad context, this maps directly to the coordinator spawning multiple agents in parallel. Each Squad member works on their assigned task independently.

## Anti-Patterns

- Parallelizing tasks that share state
- Not providing full context to each agent
- Not reviewing parallel results for conflicts
- Using parallel dispatch for sequential work

## See Also

For the full skill content, see `skills/dispatching-parallel-agents/SKILL.md` in the Superpowers repository.
