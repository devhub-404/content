# Type Sets and Underlying-type Constraints

Constraint interfaces can describe type sets using unions and approximation elements such as `~int`, which includes defined types whose underlying type is `int`. This lets generic algorithms accept domain-specific named types while preserving their exact result type.

```go
type Integer interface {
    ~int | ~int32 | ~int64
}

func Double[T Integer](value T) T {
    return value * 2
}
```

Type-set syntax is for constraints, not ordinary runtime interfaces in every context. Keep custom constraints small and semantic. A huge union of concrete implementation types usually signals that the abstraction is not actually generic.
