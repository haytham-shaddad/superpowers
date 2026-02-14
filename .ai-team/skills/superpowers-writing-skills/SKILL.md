---
name: superpowers-writing-skills
description: Create new skills following best practices — TDD applied to process documentation
domain: "meta"
confidence: "high"
source: "manual"
---

## Context

Use when creating new skills, editing existing skills, or verifying skills work before deployment. Writing skills IS Test-Driven Development applied to process documentation.

Sourced from [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent.

## Patterns

### Skill File Format (Squad-compatible)

```yaml
---
name: skill-name
description: What this skill teaches agents
domain: "e.g., testing, planning, workflow"
confidence: "low|medium|high"
source: "manual|observed|earned"
---
```

### Content Structure

1. **Context** — When and why this skill applies
2. **Patterns** — Specific patterns, conventions, or approaches
3. **Examples** — Code examples or references
4. **Anti-Patterns** — What to avoid

### Rules

- Skills must be testable — can you verify the agent follows it?
- Keep skills focused — one concept per skill
- Use concrete examples, not abstract advice
- Include anti-patterns so agents know what NOT to do

## Anti-Patterns

- Writing vague, aspirational skills ("be a good coder")
- Skills without anti-patterns section
- Skills that can't be tested
- Overly long skills that won't fit in context

## See Also

For the full skill content, see `skills/writing-skills/SKILL.md` in the Superpowers repository.
