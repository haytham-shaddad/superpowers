---
name: superpowers-git-worktrees
description: Create isolated git worktrees for feature work — smart directory selection and safety verification
domain: "workflow"
confidence: "high"
source: "manual"
---

## Context

Use when starting feature work that needs isolation from the current workspace, or before executing implementation plans. Git worktrees create isolated workspaces sharing the same repository, allowing work on multiple branches simultaneously without switching.

## Patterns

1. **Create worktree for each feature** — `git worktree add ../<project>-<feature> -b feature/<name>`
2. **Verify clean baseline** — Run tests in the new worktree before making changes
3. **Share repository** — Worktrees share the git history; no cloning needed
4. **Clean up after merge** — Remove worktrees once branches are merged

### Directory Convention

Worktrees go in a sibling directory: `../<project>-<feature-name>/`

## Examples

```bash
# Create worktree for login feature
git worktree add ../myapp-login -b feature/login

# Work in isolation
cd ../myapp-login
npm install
npm test  # verify clean baseline

# When done, clean up
git worktree remove ../myapp-login
```

## Anti-Patterns

- Working on the main branch directly for feature work
- Forgetting to run setup (npm install, etc.) in the new worktree
- Not cleaning up worktrees after merging
- Creating worktrees inside the repository directory
