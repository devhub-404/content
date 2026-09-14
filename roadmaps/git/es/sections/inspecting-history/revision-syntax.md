# Nombres de Revisión y Sintaxis de Ancestry

Muchos comandos Git aceptan una expresión de revisión, no solo un commit ID bruto. Los nombres vienen de branches/tags; sufijos `~` y `^` navegan parents y selectores de reflog se refieren a valores anteriores de refs.

```bash
git show HEAD
git show HEAD~2
git show HEAD^2
git show main@{yesterday}
```

`~n` sigue first parents repetidamente; `^n` elige un parent específico de un commit, importante en merges. La misma sintaxis funciona en log, diff, show, reset, cherry-pick, rebase y muchos otros comandos.
