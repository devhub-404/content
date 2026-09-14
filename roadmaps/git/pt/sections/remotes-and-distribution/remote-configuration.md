# Configuração de Remotes

Remote é um nome para URLs e configuração de mapeamento de refs usada em fetch/push. `origin` é apenas nome convencional criado por clone; um repositório pode ter vários remotes para forks, mirrors ou destinos separados.

```bash
git remote -v
git remote add upstream <repository-url>
git remote set-url origin <new-url>
```

Nomeie remotes pelo papel quando houver vários, como `origin` para fork e `upstream` para projeto canônico. Inspecione URLs antes de push em repositórios com destinos semelhantes ou sensíveis.
