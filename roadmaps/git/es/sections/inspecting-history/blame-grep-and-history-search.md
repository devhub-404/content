# Blame, Grep y Búsqueda en Historial

Git puede buscar contenido actual y cambios históricos. `git grep` busca contenido tracked, `git blame` anota líneas con los commits que las cambiaron por última vez y opciones pickaxe de log encuentran commits que añadieron/eliminaron texto o cambiaron patterns.

```bash
git grep "TODO"
git blame src/app.js
git log -S "oldFunction"
git log -G "pattern" -- '*.js'
```

Usa blame como navegación hacia contexto, no como juicio de responsabilidad. Abre el commit y el historial alrededor porque el ownership de línea cambia con refactors, formatting, merges y cambios mecánicos.
