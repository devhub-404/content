# Crear y Modificar Commits

Un commit registra el snapshot actual del index más metadata. Los cambios unstaged no se incluyen. Los buenos commits son checkpoints coherentes: el mensaje explica la intención y el snapshot contiene solo cambios relacionados.

```bash
git commit -m "Add login flow"
git commit --amend --no-edit
```

`--amend` sustituye el commit de la punta por un commit nuevo construido desde el index actual. Como cambia el object ID, evita amend en commits usados por colaboradores salvo reescritura coordinada.
