# Comparar Working Tree, Index e Commits

`git diff` compara dois estados sem alterá-los. Sem commits mostra mudanças unstaged; `--staged` mostra o que o próximo commit adicionaria relativo a `HEAD`; argumentos de commit/branch comparam snapshots históricos.

```bash
git diff
git diff --staged
git diff HEAD~1 HEAD
git diff main...feature
```

Comparações two-dot e three-dot respondem perguntas diferentes. Saiba se quer comparar endpoints ou mudanças desde um merge base antes de usar diff em review ou automação.
