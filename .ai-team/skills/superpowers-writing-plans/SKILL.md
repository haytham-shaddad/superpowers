---
name: "superpowers-writing-plans"
description: "Write comprehensive implementation plans with bite-sized tasks before touching code"
domain: "planning"
confidence: "high"
source: "manual"
---

## Context

Use when you have a spec or requirements for a multi-step task, before touching code. Write plans assuming the engineer has zero context and questionable taste. Document everything: which files to touch, code, testing, docs, how to verify. Bite-sized tasks (2–5 minutes each). DRY. YAGNI. TDD. Frequent commits.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Announce the skill** — "I'm using the writing-plans skill to create the implementation plan."
2. **Bite-sized tasks** — Each task should take 2–5 minutes for a single agent
3. **Exact file paths** — Every task specifies which files to touch
4. **Complete code** — Include the code to write, not just descriptions
5. **Verification steps** — Every task has a way to verify it worked
6. **TDD emphasis** — Tests come first in every task
7. **Save to docs/plans/** — Plans are persisted as dated markdown files

### Plan Format

Plans should include:
- Task number and title
- Files to create/modify
- Exact code to write (tests first)
- Verification command
- Dependencies on other tasks

## Examples

A good plan task:
```
### Task 3: Add user validation
- File: src/validators/user.js (create)
- Test: tests/validators/user.test.js (create, write first)
- Verify: npm test -- --grep "user validation"
- Depends on: Task 2 (user model)
```

## Anti-Patterns

- Writing vague tasks like "implement the feature"
- Skipping test specifications
- Tasks that take more than 10 minutes
- Plans without verification steps
- Not saving the plan to a file

## See Also

For the full skill content, see `skills/writing-plans/SKILL.md` in the Superpowers repository.
