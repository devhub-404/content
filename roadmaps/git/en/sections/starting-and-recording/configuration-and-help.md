# Configuration and Help

Git configuration can be system-wide, user-wide, repository-local, and in newer setups worktree-specific. Identity settings affect new commits, while aliases, editor choice, merge behavior, signing, and many command defaults are also configurable.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list --show-origin
git help commit
```

Use `--show-origin` when a value surprises you because multiple configuration files can contribute. Prefer documented configuration over shell aliases that hide important Git behavior, especially on shared teams.
