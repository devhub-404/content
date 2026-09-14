# `if`, `switch` y `for`

Go mantiene un control flow pequeño: `if`, `switch` y `for` cubren branching e iteración. `if`/`switch` pueden tener initializer con variables limitadas al construct. `for` es la única keyword de loop y expresa loops clásicos, while-like e infinitos.

```go
if value, err := read(); err != nil {
    return err
} else {
    fmt.Println(value)
}

for i := 0; i < 10; i++ {
    fmt.Println(i)
}
```

Los cases de `switch` no hacen fallthrough por defecto. Usa `break`, `continue`, labels y el raro `fallthrough` cuando sean más claros. Los early returns ayudan a reducir nesting.
