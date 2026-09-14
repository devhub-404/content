# Integrity Checks and Repeated Conflict Resolution

`git fsck` checks object connectivity and validity and can surface dangling or unreachable objects useful in some recovery investigations. `rerere` records how you resolved a conflict shape and can reuse that resolution when the same conflict appears again.

```bash
git fsck --full
git config rerere.enabled true
git rerere status
```

These are diagnostic and workflow tools, not substitutes for backups or clear branch policy. Before deleting unreachable objects or trusting reused conflict resolutions, inspect what Git found and verify the resulting content with tests.
