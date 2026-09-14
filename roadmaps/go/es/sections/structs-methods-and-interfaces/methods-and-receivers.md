# Methods y Receivers

Un method es una función declarada con un receiver asociado a un tipo definido. Un value receiver opera sobre una copia; un pointer receiver puede mutar el original y evita copiar structs grandes.

```go
type Counter struct {
    value int
}

func (c *Counter) Inc() {
    c.value++
}

func (c Counter) Value() int {
    return c.value
}
```

Elige un estilo consistente. Si métodos importantes necesitan pointer semantics o el tipo no debe copiarse, los receivers de puntero suelen ser adecuados. Un nil pointer receiver solo es válido si el método lo maneja deliberadamente.
