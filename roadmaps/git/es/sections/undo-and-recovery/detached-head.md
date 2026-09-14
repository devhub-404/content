# `HEAD` Detached y Recovery Seguro

En detached HEAD, `HEAD` apunta directamente a un commit en vez de una branch local. Puedes inspeccionar, construir, probar e incluso crear commits, pero ningún branch name avanza automáticamente.

```bash
git switch --detach <commit>
# experiment and commit if desired
git switch -c experiment
```

Si el trabajo debe sobrevivir, crea una branch antes de salir o recupera commits mediante reflog. Detached HEAD es un modo útil de inspección, no un error por sí mismo.
