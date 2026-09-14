# Partial Staging y Commits Enfocados

El stage por patch permite dividir edits del working tree en unidades lógicas de commit sin copiar archivos ni descartar trabajo incompleto. Git presenta hunks y eliges qué entra en el index.

```bash
git add -p
git reset -p
git commit -m "Refactor parser"
```

Un commit enfocado es más fácil de review, revert, bisect y entender después. Si un hunk mezcla cambios sin relación, divídelo o edítalo en vez de registrar coupling accidental.
