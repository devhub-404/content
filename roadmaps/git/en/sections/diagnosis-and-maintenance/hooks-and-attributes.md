# Hooks and Path Attributes

Hooks run local or server-side programs around selected Git operations, while attributes assign path-specific behavior such as text normalization, diff drivers, merge behavior, and export settings. They solve different kinds of repository automation.

```bash
# .gitattributes
*.sh text eol=lf
*.png binary

# .git/hooks/pre-commit (or configured hooks path)
# run project checks before accepting a commit
```

Client hooks are not automatically distributed merely because a repository is cloned, so do not rely on them as the only enforcement for shared policy. Version the scripts/configuration your team needs and connect them through documented setup or server checks.
