# Múltiplas Working Trees

Git worktrees permitem múltiplos diretórios checked out compartilhando objetos/refs do mesmo repositório, mas com `HEAD` e index próprios. É útil para branches paralelas, hotfixes, builds ou reviews sem stash do diretório atual.

```bash
git worktree add ../hotfix hotfix
git worktree list
git worktree remove ../hotfix
```

Uma branch normalmente não pode estar checked out em duas worktrees ao mesmo tempo. Trate linked worktrees como estado gerenciado pelo Git em vez de copiar ou remover metadata manualmente.
