# Recover with Reflog

Reflogs record recent local movements of refs such as `HEAD` and branches. Even after a reset, rebase, or deleted branch makes a commit unreachable from ordinary branch names, its object may still be recoverable while the reflog entry and underlying objects remain available.

```bash
git reflog
git show HEAD@{3}
git switch -c recovered-work <commit>
```

When recovering, first create a new branch at the desired commit rather than immediately performing another destructive reset. Reflog is local repository history and is not normally shared by fetch or push.
