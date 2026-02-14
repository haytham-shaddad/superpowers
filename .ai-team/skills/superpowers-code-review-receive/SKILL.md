---
name: superpowers-code-review-receive
description: Evaluate review feedback with technical rigor — verify suggestions before implementing, push back on incorrect feedback
domain: "quality"
confidence: "high"
source: "manual"
---

## Context

Use when receiving code review feedback, before implementing suggestions. Requires technical rigor and verification, not performative agreement or blind implementation.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

1. **Evaluate technically** — Don't blindly agree with all feedback
2. **Verify suggestions** — Test that proposed changes actually improve things
3. **Push back when wrong** — Reviewers can be wrong; explain why with evidence
4. **Acknowledge valid points** — Accept good feedback graciously
5. **Never implement without understanding** — If feedback is unclear, ask for clarification

### Response Framework

For each piece of feedback:
1. Is it technically correct?
2. Does it improve the code?
3. Is there evidence to support or refute it?
4. Respond with evidence, not emotion

## Anti-Patterns

- Agreeing with everything to avoid conflict
- Implementing suggestions without verifying they work
- Dismissing feedback without technical justification
- Making changes that break tests to satisfy a reviewer

## See Also

For the full skill content, see `skills/receiving-code-review/SKILL.md` in the Superpowers repository.
