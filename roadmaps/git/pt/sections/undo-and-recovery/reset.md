# Reset de `HEAD`, Index e Working Tree

Reset pode mover a branch atual para outro commit e opcionalmente resetar index/working tree. `--soft` move só branch; `--mixed` também reseta index; `--hard` também substitui conteúdo da working tree.

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

Isso torna reset poderoso em histórico local não publicado e perigoso com `--hard` quando há mudanças não commitadas. Não use reset em histórico compartilhado apenas para desfazer mudança publicada; revert costuma ser mais seguro.
