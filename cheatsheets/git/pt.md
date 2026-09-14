---
locale: pt
status: published
title: "Git"
slug: git
description: "Uma referência rápida de Git orientada a tarefas para mudanças, branches, remotes, histórico, undo, recovery e manutenção."
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

Referência rápida orientada a tarefas para Git no dia a dia. Comece com `git status` quando não tiver certeza do estado do repositório.

## Setup e Repositório

**Verificar a versão do Git**

```bash
git --version
```

**Configurar nome e email**

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**Ver a configuração e sua origem**

```bash
git config --list --show-origin
```

**Criar um repositório**

```bash
git init
```

**Clonar um repositório**

```bash
git clone <repository-url>
```

**Clonar para um diretório específico**

```bash
git clone <repository-url> my-project
```

**Obter ajuda de um comando**

```bash
git help commit
# or
git commit --help
```

## Status e Mudanças

**Ver o estado atual**

```bash
git status
```

**Usar status compacto**

```bash
git status --short
```

**Ver mudanças unstaged**

```bash
git diff
```

**Ver mudanças staged**

```bash
git diff --staged
```

**Ver mudanças em um arquivo**

```bash
git diff -- src/app.js
```

**Ver apenas nomes dos arquivos alterados**

```bash
git diff --name-only
```

**Ver resumo das mudanças**

```bash
git diff --stat
```

## Stage e Commits

**Fazer stage de um arquivo**

```bash
git add src/app.js
```

**Fazer stage de tudo no diretório atual**

```bash
git add .
```

**Fazer stage apenas de arquivos já tracked**

```bash
git add -u
```

Não adiciona novos arquivos untracked.

**Fazer stage de hunks selecionados**

```bash
git add -p
```

**Tirar um arquivo do stage e manter seus edits**

```bash
git restore --staged src/app.js
```

**Commitar mudanças staged**

```bash
git commit -m "Add authentication"
```

**Commitar mudanças de arquivos tracked diretamente**

```bash
git commit -am "Fix validation"
```

Não inclui novos arquivos untracked.

**Alterar a mensagem do último commit**

```bash
git commit --amend
```

**Adicionar mudanças esquecidas ao último commit**

```bash
git add forgotten-file.js
git commit --amend --no-edit
```

Evite amend em commits que colaboradores já usam, salvo reescrita compartilhada intencional.

## Branches

**Listar branches locais**

```bash
git branch
```

**Listar branches locais e remotas**

```bash
git branch -a
```

**Criar e trocar para uma branch**

```bash
git switch -c feature/login
```

**Trocar de branch**

```bash
git switch main
```

**Voltar para a branch anterior**

```bash
git switch -
```

**Renomear a branch atual**

```bash
git branch -m new-name
```

**Excluir uma branch já merged**

```bash
git branch -d feature/login
```

**Forçar exclusão de branch local**

```bash
git branch -D feature/login
```

Commits reachable apenas por essa branch podem ficar difíceis de encontrar.

**Ver branches já merged**

```bash
git branch --merged
```

**Ver branches que contêm um commit**

```bash
git branch --contains <commit>
```

## Remotes e Sincronização

**Listar remotes**

```bash
git remote -v
```

**Adicionar um remote**

```bash
git remote add origin <repository-url>
```

**Alterar URL de remote**

```bash
git remote set-url origin <repository-url>
```

**Buscar mudanças remotas**

```bash
git fetch origin
```

Fetch atualiza remote-tracking refs sem alterar sua branch atual.

**Fazer fetch e limpar branches remotas obsoletas**

```bash
git fetch --prune
```

**Fazer pull apenas com fast-forward**

```bash
git pull --ff-only
```

**Fazer pull usando rebase**

```bash
git pull --rebase
```

**Fazer push da branch atual**

```bash
git push
```

**Fazer push de nova branch e definir upstream**

```bash
git push -u origin feature/login
```

**Excluir uma branch remota**

```bash
git push origin --delete feature/login
```

**Fazer force-push com lease**

```bash
git push --force-with-lease
```

Mais seguro que --force porque verifica se a ref remota ainda é o valor esperado.

## Histórico e Busca

**Ver histórico de commits**

```bash
git log
```

**Usar histórico compacto**

```bash
git log --oneline
```

**Ver grafo de todas as refs**

```bash
git log --oneline --graph --decorate --all
```

**Ver um commit**

```bash
git show <commit>
```

**Ver histórico de um path**

```bash
git log -- path/to/file
```

**Ver quem alterou cada linha por último**

```bash
git blame path/to/file
```

**Buscar em arquivos tracked**

```bash
git grep "search text"
```

**Encontrar commits que adicionaram ou removeram uma string**

```bash
git log -S "search text"
```

**Buscar em mensagens de commit**

```bash
git log --grep="authentication"
```

## Undo e Recovery

**Descartar mudanças unstaged de um arquivo**

```bash
git restore src/app.js
```

Mudanças não commitadas nesse arquivo são perdidas.

**Descartar todas as mudanças unstaged**

```bash
git restore .
```

**Restaurar arquivo de outro commit**

```bash
git restore --source=<commit> path/to/file
```

**Desfazer último commit e manter mudanças staged**

```bash
git reset --soft HEAD~1
```

**Desfazer último commit e manter mudanças unstaged**

```bash
git reset HEAD~1
```

**Descartar último commit e suas mudanças**

```bash
git reset --hard HEAD~1
```

Perigo: --hard pode destruir mudanças não commitadas.

**Desfazer com segurança um commit publicado**

```bash
git revert <commit>
```

Cria novo commit em vez de reescrever histórico existente.

**Recuperar após reset ou rebase ruim**

```bash
git reflog
git switch -c recovered-work <commit>
```

**Salvar commits feitos em detached HEAD**

```bash
git switch -c experiment
```

## Stash

**Salvar temporariamente mudanças tracked**

```bash
git stash push -m "work in progress"
```

**Incluir arquivos untracked**

```bash
git stash push -u -m "work in progress"
```

**Listar stashes**

```bash
git stash list
```

**Inspecionar um stash**

```bash
git stash show -p stash@{0}
```

**Aplicar stash sem removê-lo**

```bash
git stash apply stash@{0}
```

**Aplicar e remover o stash mais recente**

```bash
git stash pop
```

**Excluir um stash**

```bash
git stash drop stash@{0}
```

## Merge, Rebase e Cherry-pick

**Fazer merge de uma branch na branch atual**

```bash
git merge feature/login
```

**Abortar merge em andamento**

```bash
git merge --abort
```

**Fazer rebase da branch atual sobre main**

```bash
git rebase main
```

**Reescrever commits recentes interativamente**

```bash
git rebase -i HEAD~5
```

**Continuar após resolver conflitos de rebase**

```bash
git add <resolved-files>
git rebase --continue
```

**Abortar rebase em andamento**

```bash
git rebase --abort
```

**Aplicar um commit existente aqui**

```bash
git cherry-pick <commit>
```

**Abortar cherry-pick em andamento**

```bash
git cherry-pick --abort
```

## Tags, Worktrees e Submodules

**Listar tags**

```bash
git tag
```

**Criar tag anotada**

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
```

**Fazer push de uma tag**

```bash
git push origin v1.0.0
```

**Fazer push de todas as tags**

```bash
git push --tags
```

**Criar outra working tree**

```bash
git worktree add ../hotfix hotfix
```

**Listar working trees**

```bash
git worktree list
```

**Clonar incluindo submodules**

```bash
git clone --recurse-submodules <repository-url>
```

**Inicializar e atualizar submodules**

```bash
git submodule update --init --recursive
```

## Diagnóstico e Cleanup

**Encontrar o commit que introduziu uma regressão**

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
# test, then mark each candidate good or bad
git bisect reset
```

**Ver arquivos untracked que clean excluiria**

```bash
git clean -n
```

**Excluir arquivos untracked**

```bash
git clean -f
```

Arquivos que nunca foram commitados podem ser irrecuperáveis.

**Ver arquivos e diretórios untracked que seriam excluídos**

```bash
git clean -nd
```

**Verificar integridade dos objetos do repositório**

```bash
git fsck --full
```

**Executar manutenção do repositório**

```bash
git maintenance run
# or, when appropriate
git gc
```
