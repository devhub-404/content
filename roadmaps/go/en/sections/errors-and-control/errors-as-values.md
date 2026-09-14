# Errors as Values

Go's conventional error model returns an `error` value alongside ordinary results. Callers inspect `err != nil`, handle what they understand, and propagate the rest. This keeps expected failure visible in function signatures.

```go
func load(path string) ([]byte, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        return nil, fmt.Errorf("load %q: %w", path, err)
    }
    return data, nil
}
```

Add context when crossing abstraction boundaries, usually with `%w` when the underlying error should remain discoverable. Do not log and return the same error at every layer, which creates duplicate noise. Decide which layer owns user-facing reporting.
