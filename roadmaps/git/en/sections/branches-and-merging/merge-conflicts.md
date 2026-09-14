# Resolve Merge Conflicts

A conflict means Git cannot automatically choose one combined result for some paths. During a merge the index can hold multiple stages for a conflicted path while the working file contains conflict markers or tool-produced content to resolve.

```bash
git status
# edit conflicted files
git add <resolved-files>
git merge --continue
# or: git merge --abort
```

Resolve the file into the desired final content, stage that resolved version, then continue. Use status as the source of truth, and abort when you want to return to the pre-merge state instead of improvising resets mid-conflict.
