# Qué Rastrea Git

Git es un sistema distribuido de control de versiones que registra estados del proyecto como snapshots conectados por historial. La mayoría de operaciones cotidianas son locales porque el repositorio contiene su propia base de objetos y referencias, no solo un checkout dependiente de un servidor central.

```bash
git status
git log --oneline --decorate --graph --all
```

Piensa en Git como una base de historial inmutable más nombres móviles que apuntan a ese historial. Este modelo explica branches baratas, inspección offline de commits y por qué comandos de red como fetch y push están separados de la edición local.
