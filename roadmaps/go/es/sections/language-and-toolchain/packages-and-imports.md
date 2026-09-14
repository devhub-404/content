# Packages e Imports

Todo source Go pertenece a un package, y los packages son la unidad de compilación y organización de namespace. Los archivos del mismo package contribuyen al mismo package scope, mientras los imports hacen disponibles los identifiers exportados de otros packages.

```go
package report

import (
    "fmt"
    "time"
)

func PrintNow() {
    fmt.Println(time.Now())
}
```

El nombre del package debe describir una responsabilidad coherente. Los import cycles están prohibidos, favoreciendo grafos dirigidos de dependencias. Mantén APIs pequeñas y evita buckets genéricos como `util` cuando las funciones pertenecen a dominios más claros.
