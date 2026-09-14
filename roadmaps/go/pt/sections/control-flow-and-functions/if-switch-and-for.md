# `if`, `switch` e `for`

Go mantém control flow pequeno: `if`, `switch` e `for` cobrem branching e loops. `if`/`switch` podem ter initializer com variables limitadas ao construct. `for` é a única keyword de loop e expressa loops clássicos, while-like e infinitos.

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

Cases de `switch` não fazem fallthrough por default. Use `break`, `continue`, labels e o raro `fallthrough` quando forem mais claros. Early returns ajudam a reduzir nesting.
