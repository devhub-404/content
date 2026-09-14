# Functions and Multiple Results

Functions declare parameter and result types explicitly, and Go supports returning multiple values directly. The most common use is returning a useful result plus an `error`, but multiple results also support lookups that return `(value, ok)` and other compact protocols.

```go
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

Named result parameters can document a complex signature and participate in deferred functions, but overusing them can make return flow less obvious. Prefer short functions with explicit returns unless names materially improve the contract.
