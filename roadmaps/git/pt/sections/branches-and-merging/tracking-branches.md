# Branches de Tracking e Upstream

Uma branch local pode registrar upstream usado como target default de comparação/integração em status, pull e push. Remote-tracking refs como `origin/main` são registros locais do estado de uma ref remota após o último fetch.

```bash
git branch -vv
git push -u origin feature/login
git rev-parse --abbrev-ref --symbolic-full-name @{upstream}
```

Não confunda `origin/main` com uma branch ao vivo no servidor. Fetch atualiza essa remote-tracking ref local; sua `main` local continua separada até merge, rebase, reset ou outro movimento.
