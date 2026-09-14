# Criar e Alterar Commits

Um commit registra o snapshot atual do index mais metadata. Mudanças unstaged não entram. Bons commits são checkpoints coerentes: a mensagem explica a intenção e o snapshot contém apenas mudanças relacionadas.

```bash
git commit -m "Add login flow"
git commit --amend --no-edit
```

`--amend` substitui o commit da ponta por um novo commit construído do index atual. Como o object ID muda, evite amend em commits usados por colaboradores salvo reescrita coordenada.
