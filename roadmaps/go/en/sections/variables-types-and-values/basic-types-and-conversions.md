# Basic Types and Conversions

Go has defined integer, floating-point, complex, boolean, string, and byte/rune-related types. Integer widths include machine-sized `int`/`uint` and fixed-width names such as `int32` and `uint64`. Named types are distinct even when they share an underlying representation.

```go
var age int = 42
var ratio float64 = 0.75
var enabled bool = true
var text string = "Go"

converted := float64(age)
```

Go does not perform the broad implicit numeric conversions common in C-family languages. Conversions are explicit, which makes sign and precision changes visible. Choose a type based on the API and range you need; use `int` for ordinary counts/indexes unless a fixed width or protocol representation requires another type.
