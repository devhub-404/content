# Restaurar Conteúdo da Working Tree ou Index

`git restore` copia conteúdo de arquivos de uma source escolhida para working tree e/ou index; ele não move a ponta da branch. Sem source explícita usa defaults conforme o destino restaurado.

```bash
git restore src/app.js
git restore --staged src/app.js
git restore --source=HEAD~1 src/app.js
```

Use restore quando a pergunta é “qual versão deste path deve estar na working tree ou staging area?”. Confira status/diff antes porque substituir conteúdo unstaged pode descartar edits nunca commitados.
