# Múltiples Working Trees

Git worktrees permiten varios directorios checked out compartiendo objetos/refs del mismo repositorio, pero con `HEAD` e index propios. Es útil para branches paralelas, hotfixes, builds o reviews sin stash del directorio actual.

```bash
git worktree add ../hotfix hotfix
git worktree list
git worktree remove ../hotfix
```

Una branch normalmente no puede estar checked out en dos worktrees al mismo tiempo. Trata linked worktrees como estado gestionado por Git en vez de copiar o eliminar metadata manualmente.
