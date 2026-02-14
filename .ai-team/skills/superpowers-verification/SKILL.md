---
name: "superpowers-verification"
description: "Run verification commands and confirm output before claiming work is complete — evidence before assertions"
domain: "quality"
confidence: "high"
source: "manual"
---

## Context

Use when about to claim work is complete, fixed, or passing — before committing or creating PRs. Requires running verification commands and confirming output before making any success claims.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Run all tests** — Execute the full test suite, not just the ones you think are relevant
2. **Read the output** — Actually read test output; don't assume green from the command exiting
3. **Check for regressions** — Verify that existing tests still pass
4. **Run linters** — If the project has linters, run them
5. **Build the project** — If there's a build step, run it
6. **State evidence** — "Tests pass: 47 passed, 0 failed" not "Tests should pass"

### Hard Rule

Never say "it should work" or "tests should pass." Run the commands. Report actual output.

## Examples

```
# GOOD
"All 47 tests pass. Build succeeds. Linter reports 0 issues."

# BAD
"I believe the tests should pass based on my changes."
```

## Anti-Patterns

- Claiming completion without running verification
- Running only the test you just wrote, not the full suite
- Saying "should work" instead of "verified: works"
- Skipping the build step
- Not checking linter output

## See Also

For the full skill content, see `skills/verification-before-completion/SKILL.md` in the Superpowers repository.
