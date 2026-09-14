# Branches de Tracking y Upstream

Una branch local puede registrar un upstream usado como target por defecto de comparación/integración en status, pull y push. Remote-tracking refs como `origin/main` son registros locales del estado de una ref remota tras el último fetch.

```bash
git branch -vv
git push -u origin feature/login
git rev-parse --abbrev-ref --symbolic-full-name @{upstream}
```

No confundas `origin/main` con una branch en vivo en el servidor. Fetch actualiza esa remote-tracking ref local; tu `main` local sigue separada hasta merge, rebase, reset u otro movimiento.
