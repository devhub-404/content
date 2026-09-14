# Cherry-pick Selected Commits

Cherry-pick applies the change introduced by an existing commit onto the current branch and records a new commit. It copies a change, not the original graph identity, so the source and destination commits normally have different object IDs.

```bash
git cherry-pick <commit>
git cherry-pick <oldest>^..<newest>
```

Use cherry-pick for deliberate selective transfer such as backports or one fix needed on another line. It is usually not a substitute for merging an entire branch relationship, because repeated copying can complicate later integration.
