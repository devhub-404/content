# Recuperar con Reflog

Los reflogs registran movimientos locales recientes de refs como `HEAD` y branches. Incluso tras reset, rebase o branch eliminada volver un commit unreachable por nombres ordinarios, el objeto puede seguir recuperable mientras reflog y objetos existan.

```bash
git reflog
git show HEAD@{3}
git switch -c recovered-work <commit>
```

Al recuperar, primero crea una branch nueva en el commit deseado en vez de hacer otro reset destructivo. Reflog es historial local del repositorio y normalmente no se comparte mediante fetch/push.
