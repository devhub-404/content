# Reset de `HEAD`, Index y Working Tree

Reset puede mover la branch actual a otro commit y opcionalmente resetear index/working tree. `--soft` mueve solo branch; `--mixed` también resetea index; `--hard` también reemplaza contenido del working tree.

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

Esto hace reset potente en historial local no publicado y peligroso con `--hard` cuando hay cambios no committeados. No uses reset en historial compartido solo para deshacer un cambio publicado; revert suele ser más seguro.
