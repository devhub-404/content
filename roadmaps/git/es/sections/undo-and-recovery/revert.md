# Revertir Cambios Publicados

Revert crea un commit nuevo cuyos cambios deshacen commits existentes seleccionados. El historial original sigue reachable e intacto, haciendo revert adecuado para branches compartidas donde otros dependen de los IDs existentes.

```bash
git revert <commit>
git revert --no-commit <oldest>^..<newest>
```

Revertir un merge exige mainline parent explícito y tiene implicaciones para merges futuros, así que inspecciona ancestry antes. Revert conserva historial; no borra el evento del grafo.
