# Resolver Conflictos de Merge

Un conflicto significa que Git no puede elegir automáticamente un resultado combinado para ciertos paths. Durante el merge, el index puede guardar varios stages del path mientras el working file contiene conflict markers o contenido de una merge tool.

```bash
git status
# edit conflicted files
git add <resolved-files>
git merge --continue
# or: git merge --abort
```

Edita el archivo hasta el resultado final deseado, haz stage y continúa. Usa status como fuente de verdad y abort cuando quieras volver al estado pre-merge en vez de improvisar resets durante el conflicto.
