# Variadic Functions

A variadic final parameter `...T` lets callers pass zero or more values and gives the function a slice of those values. An existing slice can be expanded at the call site with `slice...` when the parameter types match.

```go
func sum(values ...int) int {
    total := 0
    for _, value := range values {
        total += value
    }
    return total
}

total := sum(1, 2, 3)
```

Variadic functions are good for homogeneous optional lists, not for replacing a structured options type. When optional arguments have different meanings or types, a config struct or functional-options API usually communicates intent better than `...any`.
