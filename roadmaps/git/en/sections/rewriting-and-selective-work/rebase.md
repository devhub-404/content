# Rebase a Branch

Rebase takes commits unique to one line of history and reapplies equivalent changes on a new base, creating new commits. The final files can match a merge result while the ancestry graph becomes different.

```bash
git switch feature/login
git rebase main
```

Rebase local, unpublished work freely when it improves integration. Rewriting commits that others already use requires coordination because their object IDs and descendants no longer match the rewritten history.
