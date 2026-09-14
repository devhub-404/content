# `any`, Type Assertions e Type Switches

`any` é alias de empty interface e pode guardar valor de qualquer tipo. Type assertion extrai tipo dinâmico e a forma com dois resultados informa sucesso sem panic. Type switch trata múltiplas alternativas.

```go
func describe(value any) string {
    switch v := value.(type) {
    case string:
        return v
    case int:
        return strconv.Itoa(v)
    default:
        return "unknown"
    }
}
```

Use `any` em fronteiras realmente abertas, como serialization genérica ou metadata. Se as alternativas são conhecidas, API tipada com structs/interfaces/generics comunica melhor e encontra erros antes.
