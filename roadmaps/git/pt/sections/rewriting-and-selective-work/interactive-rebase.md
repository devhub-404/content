# Rebase Interativo

Interactive rebase permite editar a sequência replayed: reordenar, mudar messages, combinar, parar para editar ou remover commits. Cada commit alterado e seus descendants recebem novas identidades.

```bash
git rebase -i HEAD~5
# pick, reword, edit, squash, fixup, drop, reorder
```

Use para preparar branch local antes de publicar ou manutenção coordenada de histórico. Mantenha ponto de recovery ou confie no reflog até confirmar o resultado.
