# Restaurar Contenido del Working Tree o Index

`git restore` copia contenido de archivos desde una source elegida al working tree y/o index; no mueve la punta de la branch. Sin source explícita usa defaults según el destino restaurado.

```bash
git restore src/app.js
git restore --staged src/app.js
git restore --source=HEAD~1 src/app.js
```

Usa restore cuando la pregunta sea “¿qué versión de este path debe estar en el working tree o staging area?”. Revisa status/diff antes porque reemplazar contenido unstaged puede descartar edits nunca committeados.
