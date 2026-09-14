# Interactive Rebase

Interactive rebase lets you edit the sequence of commits being replayed: reorder them, change messages, combine commits, stop to edit one, or drop commits. Every changed commit and its descendants receive new identities.

```bash
git rebase -i HEAD~5
# pick, reword, edit, squash, fixup, drop, reorder
```

Use it to prepare a clean local topic branch before publishing or to perform deliberate coordinated history maintenance. Keep a recovery point or rely on reflog until you are satisfied with the rewritten result.
