# Find a Regression with Bisect

Bisect performs a binary search over commit ancestry between known good and bad points. Git checks out candidate commits and uses your good/bad classification to reduce the remaining search space.

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
# test each checked-out commit, then mark good/bad
git bisect reset
```

Automate the classification with `git bisect run` when you have a reliable test command. The test must distinguish good, bad, and untestable states accurately; otherwise the search can confidently point to the wrong area.
