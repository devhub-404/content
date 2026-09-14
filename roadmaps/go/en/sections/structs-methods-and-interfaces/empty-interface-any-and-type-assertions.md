# `any`, Type Assertions, and Type Switches

`any` is an alias for the empty interface and can hold a value of any type. A type assertion extracts a specific dynamic type, and the two-result form reports success without panicking. A type switch handles several dynamic alternatives.

```go
func describe(value any) string {
    switch v := value.(type) {
    case string:
        return v
    case int:
        return strconv.Itoa(v)
    default:
        return "unknown"
    }
}
```

Use `any` at genuinely open boundaries such as generic serialization, logging metadata, or reflection-heavy APIs. If the possible values form a known closed set, a typed struct/interface/generic API often communicates the contract better and catches errors earlier.
