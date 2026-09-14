# Clean Untracked Files Safely

`git clean` removes untracked working-tree files and, with options, directories or ignored files. Those files may never have been stored in Git, so deletion can be much less recoverable than resetting tracked content.

```bash
git clean -n
git clean -nd
git clean -f
git clean -fd
```

Preview with `-n` before forcing deletion and understand whether build artifacts, local databases, environment files, or generated assets are ignored versus merely untracked. Clean is a filesystem cleanup command, not a history operation.
