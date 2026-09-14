# Fast-forward vs Merge Commits

Fast-forward no es un commit especial: la ref de la branch actual simplemente avanza a un descendant porque no existe historial local divergente. `--ff-only` exige ese movimiento simple; `--no-ff` pide merge commit incluso cuando fast-forward sería posible.

```bash
git merge --ff-only origin/main
git merge --no-ff feature/login
```

Elige política según el historial que quieras preservar, no por creer que una forma de grafo sea siempre superior. Las herramientas de review pueden representar features independientemente de la estrategia final.
