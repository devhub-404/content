# Status, Archivos Tracked y Untracked

`git status` explica cómo working tree e index difieren de `HEAD` y qué archivos no están tracked. Un archivo tracked puede estar unmodified, modified, staged o tener simultáneamente una versión staged y edits más nuevos unstaged.

```bash
git status
git status --short
```

Ejecuta status antes de operaciones destructivas o que cambien historial. El formato corto es útil para checks rápidos, pero la salida completa suele indicar exactamente qué add, restore o comando de conflicto usar.
