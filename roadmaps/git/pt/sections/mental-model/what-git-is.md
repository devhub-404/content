# O que o Git Rastreia

Git é um sistema distribuído de controle de versão que registra estados do projeto como snapshots conectados por histórico. A maioria das operações cotidianas é local porque o repositório contém seu próprio banco de objetos e referências, não apenas um checkout dependente de servidor central.

```bash
git status
git log --oneline --decorate --graph --all
```

Pense no Git como um banco de histórico imutável mais nomes móveis que apontam para esse histórico. Esse modelo explica branches baratas, inspeção offline de commits e por que comandos de rede como fetch e push são separados da edição local.
