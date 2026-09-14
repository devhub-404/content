# Revision Names and Ancestry Syntax

Many Git commands accept a revision expression rather than only a raw commit ID. Names can come from branches and tags, while suffixes such as `~` and `^` navigate parents and reflog selectors can refer to earlier ref values.

```bash
git show HEAD
git show HEAD~2
git show HEAD^2
git show main@{yesterday}
```

`~n` follows first parents repeatedly; `^n` selects a specific parent of one commit, which matters for merges. Learn revision syntax because the same language works across log, diff, show, reset, cherry-pick, rebase, and many other commands.
