# Go Workspaces

Un workspace (`go.work`) permite que varios modules locales participen en el mismo build sin publicar ni añadir replace permanente en cada module. Es útil para desarrollo coordinado.

```go
// go.work
go 1.27

use (
    ./service
    ./library
)
```

Un workspace es un constructo del entorno, no sustituye la corrección independiente de cada module. Prueba los modules también como los usarían consumidores reales para que el workspace no oculte dependencias ausentes o module paths incorrectos.
