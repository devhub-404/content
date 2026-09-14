# Fazer Stage com `git add`

`git add` copia conteúdo selecionado da working tree para o index, preparando o snapshot exato do próximo commit. Rodar add novamente após novos edits atualiza a versão staged; stage não é uma relação permanente com o arquivo.

```bash
git add src/app.js
git add -p
git add -u
```

Patch mode interativo permite que apenas hunks selecionados de um arquivo entrem no commit. Isso ajuda a produzir commits focados quando a working tree contém mudanças logicamente separadas.
