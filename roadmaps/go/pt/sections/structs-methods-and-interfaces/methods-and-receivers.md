# Methods e Receivers

Method é função declarada com receiver associado a um tipo definido. Value receiver opera sobre cópia; pointer receiver pode mutar o original e evita copiar structs grandes.

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

Escolha estilo consistente. Se methods importantes precisam pointer semantics ou o tipo não deve ser copiado, receivers de ponteiro normalmente são adequados. Nil pointer receiver só é válido se o método tratar isso deliberadamente.
