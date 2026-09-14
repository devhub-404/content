# Limpiar Archivos Untracked con Seguridad

`git clean` elimina archivos untracked y, con options, directorios o ignored files. Esos archivos quizá nunca hayan sido almacenados en Git, así que la eliminación puede ser mucho menos recuperable que resetear contenido tracked.

```bash
git clean -n
git clean -nd
git clean -f
git clean -fd
```

Haz preview con `-n` antes de forzar y entiende si build artifacts, bases locales, env files o assets son ignored o solo untracked. Clean es cleanup de filesystem, no operación de historial.
