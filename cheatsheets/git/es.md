---
locale: es
status: published
title: "Git"
slug: git
description: "Una referencia rápida de Git orientada a tareas para cambios, branches, remotes, historial, undo, recovery y mantenimiento."
tags:
  - git
  - version-control
  - cheatsheet
references:
  - label: "Git Reference"
    url: https://git-scm.com/docs
  - label: "Pro Git"
    url: https://git-scm.com/book/en/v2
  - label: "Git Glossary"
    url: https://git-scm.com/docs/gitglossary
---

# Git

Referencia rápida orientada a tareas para Git del día a día. Empieza con `git status` cuando no tengas claro el estado del repositorio.

## Setup y Repositorio

**Comprobar la versión de Git**

```bash
git --version
```

**Configurar nombre y email**

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**Ver la configuración y su origen**

```bash
git config --list --show-origin
```

**Crear un repositorio**

```bash
git init
```

**Clonar un repositorio**

```bash
git clone <repository-url>
```

**Clonar en un directorio específico**

```bash
git clone <repository-url> my-project
```

**Obtener ayuda de un comando**

```bash
git help commit
# or
git commit --help
```

## Status y Cambios

**Ver el estado actual**

```bash
git status
```

**Usar status compacto**

```bash
git status --short
```

**Ver cambios unstaged**

```bash
git diff
```

**Ver cambios staged**

```bash
git diff --staged
```

**Ver cambios en un archivo**

```bash
git diff -- src/app.js
```

**Ver solo nombres de archivos modificados**

```bash
git diff --name-only
```

**Ver resumen de cambios**

```bash
git diff --stat
```

## Stage y Commits

**Hacer stage de un archivo**

```bash
git add src/app.js
```

**Hacer stage de todo en el directorio actual**

```bash
git add .
```

**Hacer stage solo de archivos ya tracked**

```bash
git add -u
```

No añade archivos nuevos untracked.

**Hacer stage de hunks seleccionados**

```bash
git add -p
```

**Quitar un archivo del stage y conservar sus edits**

```bash
git restore --staged src/app.js
```

**Committear cambios staged**

```bash
git commit -m "Add authentication"
```

**Committear cambios de archivos tracked directamente**

```bash
git commit -am "Fix validation"
```

No incluye archivos nuevos untracked.

**Cambiar el mensaje del último commit**

```bash
git commit --amend
```

**Añadir cambios olvidados al último commit**

```bash
git add forgotten-file.js
git commit --amend --no-edit
```

Evita amend en commits que colaboradores ya usan salvo reescritura compartida intencional.

## Branches

**Listar branches locales**

```bash
git branch
```

**Listar branches locales y remotas**

```bash
git branch -a
```

**Crear y cambiar a una branch**

```bash
git switch -c feature/login
```

**Cambiar de branch**

```bash
git switch main
```

**Volver a la branch anterior**

```bash
git switch -
```

**Renombrar la branch actual**

```bash
git branch -m new-name
```

**Eliminar una branch ya merged**

```bash
git branch -d feature/login
```

**Forzar eliminación de branch local**

```bash
git branch -D feature/login
```

Commits reachable solo desde esa branch pueden volverse difíciles de encontrar.

**Ver branches ya merged**

```bash
git branch --merged
```

**Ver branches que contienen un commit**

```bash
git branch --contains <commit>
```

## Remotes y Sincronización

**Listar remotes**

```bash
git remote -v
```

**Añadir un remote**

```bash
git remote add origin <repository-url>
```

**Cambiar URL de remote**

```bash
git remote set-url origin <repository-url>
```

**Obtener cambios remotos**

```bash
git fetch origin
```

Fetch actualiza remote-tracking refs sin cambiar tu branch actual.

**Hacer fetch y limpiar branches remotas obsoletas**

```bash
git fetch --prune
```

**Hacer pull solo con fast-forward**

```bash
git pull --ff-only
```

**Hacer pull usando rebase**

```bash
git pull --rebase
```

**Hacer push de la branch actual**

```bash
git push
```

**Hacer push de nueva branch y definir upstream**

```bash
git push -u origin feature/login
```

**Eliminar una branch remota**

```bash
git push origin --delete feature/login
```

**Hacer force-push con lease**

```bash
git push --force-with-lease
```

Más seguro que --force porque comprueba que la ref remota sigue siendo el valor esperado.

## Historial y Búsqueda

**Ver historial de commits**

```bash
git log
```

**Usar historial compacto**

```bash
git log --oneline
```

**Ver grafo de todas las refs**

```bash
git log --oneline --graph --decorate --all
```

**Ver un commit**

```bash
git show <commit>
```

**Ver historial de un path**

```bash
git log -- path/to/file
```

**Ver quién cambió cada línea por última vez**

```bash
git blame path/to/file
```

**Buscar en archivos tracked**

```bash
git grep "search text"
```

**Encontrar commits que añadieron o eliminaron una string**

```bash
git log -S "search text"
```

**Buscar en mensajes de commit**

```bash
git log --grep="authentication"
```

## Undo y Recovery

**Descartar cambios unstaged de un archivo**

```bash
git restore src/app.js
```

Los cambios no committeados en ese archivo se pierden.

**Descartar todos los cambios unstaged**

```bash
git restore .
```

**Restaurar archivo desde otro commit**

```bash
git restore --source=<commit> path/to/file
```

**Deshacer el último commit y mantener cambios staged**

```bash
git reset --soft HEAD~1
```

**Deshacer el último commit y mantener cambios unstaged**

```bash
git reset HEAD~1
```

**Descartar el último commit y sus cambios**

```bash
git reset --hard HEAD~1
```

Peligro: --hard puede destruir cambios no committeados.

**Deshacer de forma segura un commit publicado**

```bash
git revert <commit>
```

Crea un commit nuevo en vez de reescribir historial existente.

**Recuperar tras un reset o rebase incorrecto**

```bash
git reflog
git switch -c recovered-work <commit>
```

**Guardar commits hechos en detached HEAD**

```bash
git switch -c experiment
```

## Stash

**Guardar temporalmente cambios tracked**

```bash
git stash push -m "work in progress"
```

**Incluir archivos untracked**

```bash
git stash push -u -m "work in progress"
```

**Listar stashes**

```bash
git stash list
```

**Inspeccionar un stash**

```bash
git stash show -p stash@{0}
```

**Aplicar stash sin eliminarlo**

```bash
git stash apply stash@{0}
```

**Aplicar y eliminar el stash más reciente**

```bash
git stash pop
```

**Eliminar un stash**

```bash
git stash drop stash@{0}
```

## Merge, Rebase y Cherry-pick

**Hacer merge de una branch en la branch actual**

```bash
git merge feature/login
```

**Abortar merge en curso**

```bash
git merge --abort
```

**Hacer rebase de la branch actual sobre main**

```bash
git rebase main
```

**Reescribir commits recientes interactivamente**

```bash
git rebase -i HEAD~5
```

**Continuar tras resolver conflictos de rebase**

```bash
git add <resolved-files>
git rebase --continue
```

**Abortar rebase en curso**

```bash
git rebase --abort
```

**Aplicar aquí un commit existente**

```bash
git cherry-pick <commit>
```

**Abortar cherry-pick en curso**

```bash
git cherry-pick --abort
```

## Tags, Worktrees y Submodules

**Listar tags**

```bash
git tag
```

**Crear tag anotada**

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
```

**Hacer push de una tag**

```bash
git push origin v1.0.0
```

**Hacer push de todas las tags**

```bash
git push --tags
```

**Crear otro working tree**

```bash
git worktree add ../hotfix hotfix
```

**Listar working trees**

```bash
git worktree list
```

**Clonar incluyendo submodules**

```bash
git clone --recurse-submodules <repository-url>
```

**Inicializar y actualizar submodules**

```bash
git submodule update --init --recursive
```

## Diagnóstico y Cleanup

**Encontrar el commit que introdujo una regresión**

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
# test, then mark each candidate good or bad
git bisect reset
```

**Ver archivos untracked que clean eliminaría**

```bash
git clean -n
```

**Eliminar archivos untracked**

```bash
git clean -f
```

Archivos que nunca fueron committeados pueden ser irrecuperables.

**Ver archivos y directorios untracked que se eliminarían**

```bash
git clean -nd
```

**Comprobar integridad de objetos del repositorio**

```bash
git fsck --full
```

**Ejecutar mantenimiento del repositorio**

```bash
git maintenance run
# or, when appropriate
git gc
```
