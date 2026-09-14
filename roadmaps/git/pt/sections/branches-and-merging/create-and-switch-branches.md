# Criar e Trocar Branches

Criar branch cria uma ref móvel em um commit. `git switch` muda a branch apontada por `HEAD` e atualiza working tree/index para o snapshot correspondente, desde que mudanças locais possam ser preservadas com segurança.

```bash
git switch -c feature/login
git switch main
git branch -m feature/auth
```

Branch names descrevem linhas de trabalho, não cópias de diretórios. Mantenha mudanças commitadas ou protegidas antes de trocar quando elas conflitam com conteúdo da branch destino.
