# Cherry-pick de Commits Seleccionados

Cherry-pick aplica el cambio introducido por un commit existente en la branch actual y registra un commit nuevo. Copia el cambio, no la identidad del grafo, así que source y destination suelen tener object IDs distintos.

```bash
git cherry-pick <commit>
git cherry-pick <oldest>^..<newest>
```

Úsalo para transferencia selectiva deliberada, como backports o un fix necesario en otra línea. No es sustituto general de merge de una relación completa, porque copias repetidas complican integración posterior.
