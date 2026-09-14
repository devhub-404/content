# `if`, `switch`, and `for`

Go keeps control flow small: `if`, `switch`, and `for` cover most branching and iteration. `if` and `switch` can have initializer statements whose variables stay scoped to the construct. `for` is the only loop keyword and expresses classic loops, while-like loops, and infinite loops.

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

Go `switch` cases do not fall through by default, which removes a common source of errors. Use `break`, `continue`, labels, and the rare explicit `fallthrough` when their control effect is clearer than restructuring the function. Keep branching shallow through early returns when that improves readability.
