# Partial Staging and Focused Commits

Patch-oriented staging lets you split working-tree edits into logical commit units without first copying files or discarding unfinished work. Git presents hunks and lets you choose which pieces enter the index.

```bash
git add -p
git reset -p
git commit -m "Refactor parser"
```

A focused commit is easier to review, revert, bisect, and understand later. If one hunk mixes unrelated edits, split or edit the hunk rather than accepting accidental coupling into history.
