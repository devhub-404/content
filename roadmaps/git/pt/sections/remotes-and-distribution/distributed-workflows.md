# Forks, Upstreams e Workflows Distribuídos

Como todo clone é repositório com histórico, colaboração não exige uma topologia física única. Contributor pode pushar para fork, maintainers podem fetchar refs e projetos podem adotar workflows centrais ou multi-remote trocando os mesmos objetos Git.

```bash
git remote add upstream <canonical-url>
git fetch upstream
git rebase upstream/main
```

Separe mecânica distribuída do Git de features de review da plataforma. Pull/merge requests coordenam discussão e policy do servidor; fetch, push, branches e commits continuam sendo o modelo de dados subjacente.
