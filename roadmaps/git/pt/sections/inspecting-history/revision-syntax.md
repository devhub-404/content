# Nomes de Revisão e Sintaxe de Ancestry

Muitos comandos Git aceitam expressão de revisão, não apenas commit ID bruto. Nomes vêm de branches/tags; sufixos `~` e `^` navegam parents e seletores de reflog referem-se a valores anteriores de refs.

```bash
git show HEAD
git show HEAD~2
git show HEAD^2
git show main@{yesterday}
```

`~n` segue first parents repetidamente; `^n` escolhe um parent específico de um commit, importante em merges. A mesma sintaxe funciona em log, diff, show, reset, cherry-pick, rebase e muitos outros comandos.
