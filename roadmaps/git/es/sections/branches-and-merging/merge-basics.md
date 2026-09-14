# Hacer Merge de Branches

Merge combina historiales encontrando un ancestor común e integrando cambios de las líneas participantes. Si la branch actual puede simplemente avanzar a la otra punta, Git puede hacer fast-forward; en caso contrario puede crear un merge commit tras combinar snapshots.

```bash
git switch main
git merge feature/login
```

Merge conserva commit identities y ancestry del grafo. Es una elección natural cuando la topología de branch es historial útil o cuando reescribir commits compartidos sería inapropiado.
