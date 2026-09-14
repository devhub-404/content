# Asignación y Escape Analysis

Go decide el placement de storage mediante escape analysis. Retornar la dirección de un local es seguro porque compiler/runtime garantiza un lifetime adecuado; el objeto puede ir al heap si es necesario.

```go
func build() *int {
    value := 42
    return &value
}
```

No deformes el source basándote en suposiciones de stack/heap. Usa diagnostics y profiles cuando importen las allocations. Los mayores beneficios suelen venir de estructuras, APIs, evitar copias/conversiones y reutilizar buffers en hot paths medidos.
