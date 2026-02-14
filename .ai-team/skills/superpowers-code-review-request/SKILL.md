---
name: superpowers-code-review-request
description: Pre-review compliance checklist before requesting code review — verify work meets requirements first
domain: "quality"
confidence: "high"
source: "manual"
---

## Context

Use when completing tasks, implementing major features, or before merging to verify work meets requirements. Dispatch a code reviewer subagent to catch issues before they cascade.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Self-check first** — Run through compliance checklist before requesting review
2. **Dispatch reviewer** — Use a dedicated reviewer agent (not the implementing agent)
3. **Categorize issues** — Critical (must fix), Important (should fix), Suggestions (nice to have)
4. **Block on criticals** — Critical issues block progress

### Pre-Review Checklist

- [ ] All tests pass
- [ ] Code follows project conventions
- [ ] Changes match the plan/spec
- [ ] No unrelated changes included
- [ ] Documentation updated if needed

## Anti-Patterns

- Requesting review before running tests
- Self-reviewing without a separate agent/person
- Ignoring review feedback
- Not categorizing issue severity

## See Also

For the full skill content, see `skills/requesting-code-review/SKILL.md` in the Superpowers repository.
