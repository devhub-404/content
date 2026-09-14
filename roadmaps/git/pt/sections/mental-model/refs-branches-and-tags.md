# Refs, Branches e Tags

Uma ref é um nome legível que aponta para object ID ou outra ref. Branches locais vivem em `refs/heads`, tags em `refs/tags` e `HEAD` normalmente aponta simbolicamente para a branch atual.

```bash
git branch --show-current
git show-ref --heads --tags
```

Branches são refs móveis: commitar avança a branch atual. Tags normalmente são nomes estáveis para releases ou pontos importantes. Por isso criar branch é barato: cria um nome, não uma cópia do projeto.
