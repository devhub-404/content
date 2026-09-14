# `errors.Is`, `errors.As`, and Wrapping

Wrapped errors form an error chain. `errors.Is` asks whether an error matches a target through that chain, while `errors.As` finds an error assignable to a requested type. This lets APIs add context without forcing callers to parse strings.

```go
if errors.Is(err, os.ErrNotExist) {
    // handle missing file
}

var pathErr *fs.PathError
if errors.As(err, &pathErr) {
    fmt.Println(pathErr.Path)
}
```

Define sentinel or typed errors only when callers have a meaningful recovery branch based on that identity. Error messages remain for humans; program logic should use structured error relationships. Wrapping an error can become part of an API contract, so change it deliberately.
