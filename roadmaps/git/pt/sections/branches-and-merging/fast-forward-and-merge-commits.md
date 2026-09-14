# Fast-forward vs Merge Commits

Fast-forward não é commit especial: a ref da branch atual apenas avança para um descendant porque não existe histórico divergente local. `--ff-only` exige esse movimento simples; `--no-ff` pede merge commit mesmo quando fast-forward seria possível.

```bash
git merge --ff-only origin/main
git merge --no-ff feature/login
```

Escolha política conforme o histórico que deseja preservar, não pela crença de que um formato de grafo é sempre superior. Ferramentas de review podem representar features independentemente da estratégia final.
