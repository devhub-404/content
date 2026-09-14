# Allocation and Escape Analysis

Go determines storage placement through escape analysis. Returning the address of a local value is safe because the compiler/runtime ensures the object lives long enough; it may be moved to heap storage when necessary.

```go
func build() *int {
    value := 42
    return &value
}
```

Do not contort source code based on guesses about stack versus heap. Use compiler diagnostics and profiles when allocations matter. The biggest wins usually come from data structure and API choices, avoiding needless conversions/copies, and reusing buffers in measured hot paths.
