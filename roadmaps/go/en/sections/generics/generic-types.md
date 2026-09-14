# Generic Types

A generic type is parameterized by one or more type arguments and can use those parameters in fields and methods. Each instantiation such as `Stack[int]` has a statically known element type without requiring `any` and type assertions.

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

The zero value of a type parameter can be produced by declaring `var zero T`. Design generic containers so their zero value is useful when practical, just like ordinary Go types. Keep the constraints as weak as the implementation needs.
