# Multiple Working Trees

Git worktrees let one repository have multiple checked-out working directories, each with its own `HEAD` and index while sharing most repository objects and refs. This is useful for parallel branches, hotfixes, builds, or reviews without stashing the current directory.

```bash
git worktree add ../hotfix hotfix
git worktree list
git worktree remove ../hotfix
```

A branch normally cannot be checked out in two ordinary worktrees simultaneously. Treat linked worktrees as repository state managed by Git rather than copying or manually deleting their internal metadata.
