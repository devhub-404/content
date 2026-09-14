# Type Parameters and Constraints

Generic functions and types declare type parameters with constraints. A constraint is an interface used in the type-parameter context to describe the permitted type set and methods/operations that generic code may use.

```go
func Max[T cmp.Ordered](a, b T) T {
    if a > b {
        return a
    }
    return b
}
```

Use generics when an algorithm or data structure truly preserves a relationship across multiple types. Do not replace small behavior-oriented interfaces with type parameters automatically. Interfaces provide runtime polymorphism; generics provide compile-time type parameterization, and each fits different APIs.
