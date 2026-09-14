# Interfaces and Implicit Satisfaction

An interface describes a set of methods, and a concrete type satisfies it implicitly by having the required method set. There is no `implements` declaration, which keeps dependencies flowing from consumers toward the small behavior they need.

```go
type Writer interface {
    Write([]byte) (int, error)
}

func save(w Writer, data []byte) error {
    _, err := w.Write(data)
    return err
}
```

Prefer small interfaces defined near the consumer. A function that only needs `Write` should not accept a large service interface. Implicit satisfaction enables easy substitution and testing, but the method set rules for `T` and `*T` still matter when receivers differ.
