# Working Tree, Index y `HEAD`

El working tree contiene los archivos que editas. El index, también llamado staging area, guarda el snapshot preparado para el próximo commit. `HEAD` normalmente identifica la branch actual y por tanto el commit usado como baseline histórico.

```bash
git status
git diff
git diff --staged
```

`git diff` compara working tree con index; `git diff --staged` compara index con `HEAD`. Este modelo de tres estados es la base para entender add, restore, reset, commit y resolución de conflictos.
