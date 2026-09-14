# Identifiers Exportados y Documentación

Go usa mayúsculas para la visibilidad entre packages: un identifier que empieza por una letra Unicode mayúscula se exporta. Así la API pública es visible directamente en el source sin un sistema separado de access modifiers.

```go
package geometry

// Point represents a location in 2D space.
type Point struct {
    X float64
    Y float64
}
```

Los comentarios de documentación en declarations exportadas forman parte del diseño normal y aparecen en `go doc`/pkg.go.dev. Explica el contrato, no repitas solo el nombre. Mantén los detalles de implementación sin exportar con nombres en minúscula.
