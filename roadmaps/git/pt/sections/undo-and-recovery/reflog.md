# Recuperar com Reflog

Reflogs registram movimentos locais recentes de refs como `HEAD` e branches. Mesmo após reset, rebase ou branch deletada tornar commit unreachable pelos nomes comuns, o objeto pode continuar recuperável enquanto reflog e objetos existirem.

```bash
git reflog
git show HEAD@{3}
git switch -c recovered-work <commit>
```

Ao recuperar, primeiro crie nova branch no commit desejado em vez de fazer outro reset destrutivo. Reflog é histórico local do repositório e normalmente não é compartilhado por fetch/push.
