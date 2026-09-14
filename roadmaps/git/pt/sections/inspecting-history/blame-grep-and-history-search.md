# Blame, Grep e Busca no Histórico

Git consegue buscar conteúdo atual e mudanças históricas. `git grep` busca conteúdo tracked, `git blame` anota linhas com commits que as alteraram por último e opções pickaxe de log encontram commits que adicionaram/removeram texto ou mudaram patterns.

```bash
git grep "TODO"
git blame src/app.js
git log -S "oldFunction"
git log -G "pattern" -- '*.js'
```

Use blame como navegação para contexto, não como julgamento de responsabilidade. Abra o commit e histórico ao redor porque ownership de linha muda com refactors, formatting, merges e mudanças mecânicas.
