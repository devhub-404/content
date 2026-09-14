# `go.mod` y Module Paths

Un module agrupa packages versionados y se identifica mediante un module path declarado en `go.mod`. El archivo también registra expectativas de versión Go/toolchain y dependencies del grafo.

```go
module example.com/project

go 1.27

require example.com/dependency v1.4.0
```

Los module paths pasan a formar parte de los import paths y de la API pública al publicar. Elígelos deliberadamente. Versiona `go.mod`/`go.sum` y usa comandos estándar en vez de editar checksums manualmente.
