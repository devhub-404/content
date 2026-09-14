# Encontrar una Regresión con Bisect

Bisect hace búsqueda binaria sobre ancestry entre puntos conocidos good y bad. Git hace checkout de candidates y usa tu clasificación para reducir el espacio restante.

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
# test each checked-out commit, then mark good/bad
git bisect reset
```

Automatiza con `git bisect run` cuando tengas un comando de test fiable. El test debe distinguir good, bad y untestable correctamente; de lo contrario la búsqueda puede apuntar al área equivocada.
