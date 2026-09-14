# `errors.Is`, `errors.As` y Wrapping

Los errores wrapped forman una cadena. `errors.Is` busca un target a lo largo de ella y `errors.As` encuentra un error compatible con un tipo. Así las APIs añaden contexto sin obligar a parsear strings.

```go
if errors.Is(err, os.ErrNotExist) {
    // handle missing file
}

var pathErr *fs.PathError
if errors.As(err, &pathErr) {
    fmt.Println(pathErr.Path)
}
```

Define sentinel/typed errors solo cuando los callers tengan un recovery significativo basado en esa identidad. Los mensajes son para humanos; la lógica debe usar relaciones estructuradas. El wrapping puede formar parte del contrato público.
