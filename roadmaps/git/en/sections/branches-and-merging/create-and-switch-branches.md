# Create and Switch Branches

Creating a branch creates a movable ref at a commit. `git switch` changes which branch `HEAD` points to and updates the working tree/index to that branch's snapshot, provided local changes can be preserved safely.

```bash
git switch -c feature/login
git switch main
git branch -m feature/auth
```

Branch names describe lines of work, not copies of directories. Keep changes committed or otherwise safely managed before switching when they overlap with target-branch content.
