# Rebase Interactivo

Interactive rebase permite editar la secuencia replayed: reordenar, cambiar messages, combinar, parar para editar o eliminar commits. Cada commit alterado y sus descendants reciben nuevas identidades.

```bash
git rebase -i HEAD~5
# pick, reword, edit, squash, fixup, drop, reorder
```

Úsalo para preparar una branch local antes de publicar o para mantenimiento coordinado de historial. Mantén un punto de recovery o confía en reflog hasta confirmar el resultado.
