# Revert Published Changes

Revert creates a new commit whose changes reverse the selected existing commit or commits. The original history remains reachable and unchanged, which makes revert suitable for shared branches where collaborators may already depend on those commit IDs.

```bash
git revert <commit>
git revert --no-commit <oldest>^..<newest>
```

Reverting a merge needs an explicit mainline parent and has deeper future-merge implications, so inspect the merge ancestry before doing it. Revert is a history-preserving undo, not a way to erase an event from the graph.
