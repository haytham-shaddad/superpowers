---
name: "superpowers-systematic-debugging"
description: "4-phase root cause analysis — observe, hypothesize, test, fix — before proposing any fixes"
domain: "debugging"
confidence: "high"
source: "manual"
---

## Context

Use when encountering any bug, test failure, or unexpected behavior, before proposing fixes. Random fixes waste time and create new bugs. Quick patches mask underlying issues.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

### 4-Phase Process

1. **Observe** — Reproduce the issue, gather evidence, read error messages carefully
2. **Hypothesize** — Form a theory about root cause based on evidence
3. **Test the hypothesis** — Add logging, write a failing test, or isolate the variable
4. **Fix** — Apply targeted fix to the root cause, verify with tests

### Rules

- Never propose a fix before understanding the root cause
- One change at a time when debugging
- Verify the fix actually addresses the root cause (not just symptoms)
- Add a regression test for every bug fix

## Examples

**Bug:** "Login sometimes fails"
1. **Observe:** Check logs, reproduce, identify pattern (fails after 30min)
2. **Hypothesize:** Token expiration not handled
3. **Test:** Add logging around token refresh, reproduce → confirmed
4. **Fix:** Handle token refresh, add test for expired token flow

## Anti-Patterns

- "Let me try this quick fix" without understanding the problem
- Changing multiple things at once
- Fixing symptoms instead of root causes
- Not adding regression tests
- Assuming the first hypothesis is correct without testing it

## See Also

For the full skill content, see `skills/systematic-debugging/SKILL.md` in the Superpowers repository.
