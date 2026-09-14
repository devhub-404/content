# `go.mod` e Module Paths

Module agrupa packages versionados e é identificado por module path em `go.mod`. O arquivo também registra expectativas de versão Go/toolchain e dependencies do grafo.

```go
module example.com/project

go 1.27

require example.com/dependency v1.4.0
```

Module paths viram parte dos import paths e da API pública quando publicados. Escolha deliberadamente. Versione `go.mod`/`go.sum` e use comandos padrão em vez de editar checksums manualmente.
