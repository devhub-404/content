# `any`, Type Assertions y Type Switches

`any` es alias de la empty interface y puede contener un valor de cualquier tipo. Una type assertion extrae el tipo dinámico y la forma de dos resultados informa el éxito sin panic. Un type switch maneja varias alternativas.

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

Usa `any` en fronteras realmente abiertas, como serialización genérica o metadata. Si las alternativas son conocidas, una API tipada con structs/interfaces/generics comunica mejor y detecta errores antes.
