# Working Tree, Index e `HEAD`

A working tree contém os arquivos que você edita. O index, também chamado staging area, guarda o snapshot preparado para o próximo commit. `HEAD` normalmente identifica a branch atual e, portanto, o commit usado como baseline histórico.

```bash
git status
git diff
git diff --staged
```

`git diff` compara working tree com index; `git diff --staged` compara index com `HEAD`. Esse modelo de três estados é a base para entender add, restore, reset, commit e resolução de conflitos.
