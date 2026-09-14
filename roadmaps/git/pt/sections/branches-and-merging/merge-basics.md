# Fazer Merge de Branches

Merge combina históricos encontrando ancestor comum e integrando mudanças das linhas participantes. Se a branch atual pode apenas avançar para a outra ponta, Git pode fazer fast-forward; caso contrário pode criar merge commit após combinar snapshots.

```bash
git switch main
git merge feature/login
```

Merge preserva commit identities e ancestry do grafo. É escolha natural quando a topologia da branch é histórico útil ou quando reescrever commits compartilhados seria inadequado.
