# Ler Histórico com `log` e `show`

`git log` percorre histórico reachable e pode filtrar, formatar, desenhar o grafo e limitar o traversal. `git show` exibe um objeto, normalmente commit com metadata e patch.

```bash
git log --oneline --graph --decorate --all
git show --stat HEAD
git log -- path/to/file
```

Histórico é grafo, então filtros de path, author, date, ancestry e grep mudam o que aparece. Monte o log conforme a pergunta em vez de decorar um formato enorme.
