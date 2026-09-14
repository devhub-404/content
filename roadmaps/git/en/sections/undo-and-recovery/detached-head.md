# Detached `HEAD` and Safe Recovery

In detached-HEAD state, `HEAD` points directly to a commit rather than to a local branch ref. You can inspect, build, test, and even create new commits, but no branch name automatically advances with those commits.

```bash
git switch --detach <commit>
# experiment and commit if desired
git switch -c experiment
```

If the work should survive, create a branch before leaving or recover the commits through reflog afterward. Detached HEAD is a useful inspection mode, not itself an error.
