# Tipos Genéricos

Tipo genérico é parametrizado por type arguments e pode usá-los em fields/methods. Cada instantiation como `Stack[int]` preserva element type sem `any` e assertions.

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

Zero value de type parameter pode ser obtido com `var zero T`. Projete generic containers com zero value útil quando possível e mantenha constraints apenas tão fortes quanto a implementação exige.
