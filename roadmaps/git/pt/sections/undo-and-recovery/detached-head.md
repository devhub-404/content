# `HEAD` Detached e Recovery Seguro

Em detached HEAD, `HEAD` aponta diretamente para commit em vez de branch local. Você pode inspecionar, buildar, testar e até criar commits, mas nenhum branch name avança automaticamente.

```bash
git switch --detach <commit>
# experiment and commit if desired
git switch -c experiment
```

Se o trabalho deve sobreviver, crie branch antes de sair ou recupere commits via reflog. Detached HEAD é modo útil de inspeção, não um erro por si só.
