# `errors.Is`, `errors.As` e Wrapping

Errors wrapped formam cadeia. `errors.Is` verifica target ao longo dela e `errors.As` encontra erro compatível com um tipo. Assim APIs adicionam contexto sem obrigar parsing de strings.

```go
if errors.Is(err, os.ErrNotExist) {
    // handle missing file
}

var pathErr *fs.PathError
if errors.As(err, &pathErr) {
    fmt.Println(pathErr.Path)
}
```

Defina sentinel/typed errors apenas quando callers têm recovery significativo baseado nessa identidade. Mensagens são para humanos; lógica deve usar relações estruturadas. Wrapping pode virar parte do contrato público.
