# Hacer Stage con `git add`

`git add` copia contenido seleccionado del working tree al index, preparando el snapshot exacto del próximo commit. Ejecutar add de nuevo tras nuevos edits actualiza la versión staged; el stage no es una relación permanente con el archivo.

```bash
git add src/app.js
git add -p
git add -u
```

El patch mode interactivo permite que solo hunks seleccionados de un archivo entren en el commit. Esto ayuda a producir commits enfocados cuando el working tree contiene cambios lógicamente separados.
