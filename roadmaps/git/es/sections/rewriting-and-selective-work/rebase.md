# Hacer Rebase de una Branch

Rebase toma commits exclusivos de una línea y reaplica cambios equivalentes sobre una nueva base, creando commits nuevos. Los archivos finales pueden coincidir con un merge mientras el grafo de ancestry queda distinto.

```bash
git switch feature/login
git rebase main
```

Haz rebase libremente sobre trabajo local no publicado cuando ayude a integrar. Reescribir commits usados por otros exige coordinación porque object IDs y descendants dejan de coincidir.
