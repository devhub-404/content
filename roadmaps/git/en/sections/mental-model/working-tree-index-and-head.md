# Working Tree, Index, and `HEAD`

The working tree is the files you edit. The index, also called the staging area, stores the snapshot you are preparing for the next commit. `HEAD` normally identifies the current branch and therefore the commit that serves as your current historical baseline.

```bash
git status
git diff
git diff --staged
```

`git diff` compares working-tree changes with the index, while `git diff --staged` compares the index with `HEAD`. This three-state model is the foundation for understanding add, restore, reset, commit, and many conflict-resolution workflows.
