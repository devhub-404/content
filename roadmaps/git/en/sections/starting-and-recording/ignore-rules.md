# Ignore Rules and Excludes

Ignore rules affect untracked files that Git should normally not offer for staging. `.gitignore` is versioned project policy; repository-local excludes and global excludes can hold machine- or user-specific patterns.

```bash
# .gitignore
node_modules/
*.log
.env.local
!important.log
```

Ignoring does not untrack a file already present in history. Remove it from the index deliberately if the project should stop tracking it, and never treat ignore files as a security mechanism for secrets that were already committed.
