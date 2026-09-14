# Reverter Mudanças Publicadas

Revert cria novo commit cujas mudanças desfazem commits existentes selecionados. O histórico original continua reachable e intacto, tornando revert adequado a branches compartilhadas onde outros dependem dos IDs existentes.

```bash
git revert <commit>
git revert --no-commit <oldest>^..<newest>
```

Reverter merge exige mainline parent explícito e tem implicações para merges futuros, então inspecione ancestry antes. Revert preserva histórico; não apaga o evento do grafo.
