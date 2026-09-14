# Comparar Working Tree, Index y Commits

`git diff` compara dos estados sin modificarlos. Sin commits muestra cambios unstaged; `--staged` muestra lo que el próximo commit añadiría respecto a `HEAD`; argumentos de commit/branch comparan snapshots históricos.

```bash
git diff
git diff --staged
git diff HEAD~1 HEAD
git diff main...feature
```

Las comparaciones two-dot y three-dot responden preguntas distintas. Decide si quieres comparar endpoints o cambios desde un merge base antes de usar diff en review o automatización.
