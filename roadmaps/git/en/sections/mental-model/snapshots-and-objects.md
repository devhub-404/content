# Snapshots and Git Objects

A commit does not store a patch as its primary model; it names a tree snapshot and records metadata such as parents, author, committer, and message. Trees describe directory entries, blobs store file contents, commits connect snapshots, and annotated tags can point to other objects.

```bash
git cat-file -t HEAD
git cat-file -p HEAD
```

Objects are content-addressed by object IDs. You rarely need plumbing commands in normal work, but understanding objects makes branching, deduplication, recovery, and history rewriting much less mysterious.
