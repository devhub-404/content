# Comando `go` y Workflow Diario

El comando `go` es el centro del toolchain estándar. Compila packages, ejecuta programas y tests, gestiona dependencies, instala binaries y consulta metadata de packages/modules. Un proyecto Go suele necesitar mucha menos configuración de build personalizada que otros ecosistemas compilados.

```go
// Typical commands:
// go run .
// go test ./...
// go fmt ./...
// go vet ./...
// go build ./...
```

Usa las herramientas estándar como workflow por defecto antes de añadir wrappers. `gofmt` define el formato, `go test` es el runner normal, `go vet` detecta construcciones sospechosas y `go build` sigue el grafo de modules/packages. Las convenciones facilitan mantenimiento y CI.
