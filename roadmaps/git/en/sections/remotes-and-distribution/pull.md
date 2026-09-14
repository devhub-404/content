# Pull and Integration Strategy

Pull performs a fetch and then integrates the selected upstream into the current branch. The integration step may fast-forward, merge, or rebase depending on options and configuration, so “pull” is not one universal history shape.

```bash
git pull --ff-only
git pull --rebase
git pull --no-rebase
```

Choose an explicit team strategy and configure it rather than relying on surprises. If you want maximum visibility, fetch first, inspect the remote-tracking branch, and then run the merge or rebase operation separately.
