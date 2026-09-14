# Stash Temporary Work

Stash records selected dirty working-tree and index state so you can return to a cleaner checkout without making an ordinary project-history commit. Stash entries are Git objects referenced through a special reflog-like stack.

```bash
git stash push -m "WIP parser"
git stash list
git stash pop
```

Use stash for genuinely temporary context switches, not as a long-term task tracker. Named small commits on a temporary branch are often easier to understand, share, recover, and review when work will live for more than a short interruption.
