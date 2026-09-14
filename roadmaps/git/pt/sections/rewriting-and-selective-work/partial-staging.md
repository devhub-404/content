# Partial Staging e Commits Focados

Stage por patch permite dividir edits da working tree em unidades lógicas de commit sem copiar arquivos ou descartar trabalho incompleto. Git apresenta hunks e você escolhe o que entra no index.

```bash
git add -p
git reset -p
git commit -m "Refactor parser"
```

Commit focado é mais fácil de review, revert, bisect e entender depois. Se um hunk mistura mudanças sem relação, divida ou edite em vez de registrar coupling acidental.
