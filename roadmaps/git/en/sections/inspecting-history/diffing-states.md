# Compare Working Tree, Index, and Commits

`git diff` compares two states without changing them. With no commit arguments it shows unstaged changes; `--staged` shows what the next commit would add relative to `HEAD`; commit and branch arguments compare historical snapshots.

```bash
git diff
git diff --staged
git diff HEAD~1 HEAD
git diff main...feature
```

Two-dot and three-dot branch comparisons answer different questions. Learn whether you want endpoint-to-endpoint differences or changes introduced since a merge base before using a diff as evidence in reviews or automation.
