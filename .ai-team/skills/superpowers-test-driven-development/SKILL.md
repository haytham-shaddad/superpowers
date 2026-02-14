---
name: superpowers-test-driven-development
description: RED-GREEN-REFACTOR cycle — write the test first, watch it fail, write minimal code to pass
domain: "testing"
confidence: "high"
source: "manual"
---

## Context

Use when implementing any feature or bugfix, before writing implementation code. This is a rigid skill — follow it exactly. Don't adapt away from the discipline.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

### The Cycle

1. **RED** — Write a failing test that describes the desired behavior
2. **Confirm RED** — Run the test, verify it fails for the expected reason
3. **GREEN** — Write the minimum code to make the test pass
4. **Confirm GREEN** — Run the test, verify it passes
5. **REFACTOR** — Clean up while keeping tests green
6. **COMMIT** — Commit after each green cycle

### Rules

- Never write implementation code before a failing test
- If you wrote code before tests, delete it and start over
- One behavior per test
- Test the interface, not the implementation
- If a test is hard to write, the design needs work

## Examples

```
# BAD: Writing code first
function add(a, b) { return a + b; }
// then writing test... NO

# GOOD: Test first
test("add returns sum of two numbers", () => {
  expect(add(2, 3)).toBe(5);
});
// Run → FAIL (add not defined)
// Write minimal implementation
// Run → PASS
// Commit
```

## Anti-Patterns

- Writing implementation before tests ("I'll add tests later")
- Writing multiple tests before any implementation
- Testing implementation details instead of behavior
- Skipping the RED step (test must fail first)
- Large refactoring steps that break tests

## See Also

For the full skill content, see `skills/test-driven-development/SKILL.md` in the Superpowers repository.
