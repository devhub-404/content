# Tipos Genéricos

Un tipo genérico está parametrizado por type arguments y puede usarlos en fields/methods. Cada instantiation como `Stack[int]` conserva el element type sin `any` ni assertions.

```go
type Stack[T any] struct {
    items []T
}

func (s *Stack[T]) Push(value T) {
    s.items = append(s.items, value)
}

func (s *Stack[T]) Pop() (T, bool) {
    var zero T
    if len(s.items) == 0 {
        return zero, false
    }
    last := len(s.items) - 1
    value := s.items[last]
    s.items = s.items[:last]
    return value, true
}
```

El zero value de un type parameter puede obtenerse con `var zero T`. Diseña generic containers con zero value útil cuando sea posible y mantén los constraints tan débiles como requiera la implementación.
