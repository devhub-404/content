# Errors como Valores

El modelo convencional de errores retorna `error` junto al resultado. Los callers comprueban `err != nil`, manejan lo que entienden y propagan el resto, manteniendo el fallo esperado visible en la firma.

```go
func load(path string) ([]byte, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        return nil, fmt.Errorf("load %q: %w", path, err)
    }
    return data, nil
}
```

Añade contexto al cruzar abstracciones, normalmente con `%w` cuando la causa debe seguir siendo discoverable. No hagas log y return del mismo error en cada layer. Define qué capa posee el reporting al usuario.
