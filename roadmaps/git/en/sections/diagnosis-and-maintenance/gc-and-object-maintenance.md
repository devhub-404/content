# Garbage Collection and Repository Maintenance

Git stores loose and packed objects and periodically performs maintenance to optimize storage and reachability bookkeeping. Normal porcelain commands often trigger safe automatic maintenance, so manual `git gc` is not something most developers need after every workflow.

```bash
git count-objects -vH
git gc
git maintenance run
```

Large or long-lived repositories may benefit from scheduled maintenance, commit-graph updates, and repacking. Measure repository behavior and use Git's maintenance mechanisms rather than deleting `.git/objects` content manually.
