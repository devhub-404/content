# What Git Tracks

Git is a distributed version-control system that records project states as snapshots connected by history. Most everyday operations are local because a repository contains its own object database and references, not merely a checkout that depends on a central server.

```bash
git status
git log --oneline --decorate --graph --all
```

Think of Git as a database of immutable history plus movable names that point into that history. This model explains why branches are cheap, commits can be inspected offline, and network commands such as fetch and push are separate from ordinary local editing.
