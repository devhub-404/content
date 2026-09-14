# Fetch Remote History

Fetch contacts a remote, downloads missing objects, and updates configured remote-tracking refs without integrating those commits into the current branch. This separation lets you inspect incoming history before deciding how local branches should move.

```bash
git fetch origin
git fetch --all --prune
```

`--prune` removes local remote-tracking refs for remote branches that no longer exist according to the fetch configuration. Fetch is usually the safest first network operation when you want information without changing local branch history.
