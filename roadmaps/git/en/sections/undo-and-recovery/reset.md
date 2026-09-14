# Reset `HEAD`, Index, and Working Tree

Reset can move the current branch to another commit and then optionally reset the index and working tree. `--soft` moves the branch only; the default `--mixed` also resets the index; `--hard` also replaces working-tree content.

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

This makes reset powerful for unpublished local history and dangerous when `--hard` would destroy uncommitted changes. Do not use reset on shared branch history merely because you want to undo a published change; revert is usually the safer collaboration tool.
