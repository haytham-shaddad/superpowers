---
name: superpowers-finishing-branch
description: Guide completion of development work — verify tests, present merge/PR/keep/discard options, clean up worktree
domain: "workflow"
confidence: "high"
source: "manual"
---

## Context

Use when implementation is complete, all tests pass, and you need to decide how to integrate the work. Guides completion by presenting structured options.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Verify all tests pass** — Run the full test suite one final time
2. **Present options:**
   - **Merge** — Merge directly into the target branch
   - **PR** — Create a pull request for review
   - **Keep** — Keep the branch for more work later
   - **Discard** — Remove the branch and worktree
3. **Clean up** — Remove worktree after merge/discard
4. **Let the human decide** — Present options, don't assume

## Anti-Patterns

- Auto-merging without asking
- Forgetting to clean up worktrees
- Leaving branches dangling without a clear plan
- Not running final verification before presenting options

## See Also

For the full skill content, see `skills/finishing-a-development-branch/SKILL.md` in the Superpowers repository.
