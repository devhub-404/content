# Refs, Branches, and Tags

A ref is a human-meaningful name that points to an object ID or another ref. Local branches live under `refs/heads`, tags under `refs/tags`, and `HEAD` normally points symbolically to the current branch.

```bash
git branch --show-current
git show-ref --heads --tags
```

Branches are movable refs: committing advances the current branch. Tags are normally stable names used for releases or important points. This is why creating a branch is cheap—it creates a name, not a copy of the project.
