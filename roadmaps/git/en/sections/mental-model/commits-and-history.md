# Commits and Parent History

A commit names one snapshot and usually one parent commit; merge commits have multiple parents. Following parent links produces the repository history as a directed graph rather than as one universal linear sequence.

```bash
git show --stat HEAD
git log --oneline --parents -5
```

A branch moves to a new commit when you commit on that branch. Commit IDs change when commit content or metadata changes, which is why rebasing or amending creates new commits even when the final files look similar.
