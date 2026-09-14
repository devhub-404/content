# Fast-forward vs Merge Commits

A fast-forward is not a special commit: the current branch ref moves directly to a descendant commit because no divergent local history exists. `--ff-only` requires that simple move, while `--no-ff` requests a merge commit even when fast-forwarding is possible.

```bash
git merge --ff-only origin/main
git merge --no-ff feature/login
```

Choose repository policy based on the history you want to preserve, not on the belief that one graph shape is universally cleaner. Review tools can often represent feature branches independently of whether the final integration uses a merge commit.
