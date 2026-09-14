# Merge Branches

Merging combines histories by finding a common ancestor and integrating changes made on the participating lines. If the current branch can simply advance to the other tip, Git can fast-forward; otherwise it may create a merge commit after combining snapshots.

```bash
git switch main
git merge feature/login
```

Merge preserves the existing commit identities and graph ancestry. This makes it a natural integration choice when the branch topology itself is useful history or when rewriting already-shared commits would be inappropriate.
