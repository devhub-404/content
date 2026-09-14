# Errors como Valores

Modelo convencional de erro retorna `error` junto ao resultado. Callers verificam `err != nil`, tratam o que entendem e propagam o restante, mantendo falha esperada visível na assinatura.

```go
func load(path string) ([]byte, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        return nil, fmt.Errorf("load %q: %w", path, err)
    }
    return data, nil
}
```

Adicione contexto ao cruzar abstrações, normalmente com `%w` quando a causa deve permanecer discoverable. Não logue e retorne o mesmo erro em cada layer. Defina qual layer possui reporting ao usuário.
