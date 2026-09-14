# Create and Amend Commits

A commit records the current index snapshot plus metadata. Unstaged working-tree changes are not included. Good commits are coherent checkpoints: their message explains the intent while the snapshot contains only the changes that support that intent.

```bash
git commit -m "Add login flow"
git commit --amend --no-edit
```

`--amend` replaces the tip commit with a new commit built from the current index and chosen message. Because the object ID changes, avoid amending commits that collaborators have already based work on unless history rewriting is coordinated.
