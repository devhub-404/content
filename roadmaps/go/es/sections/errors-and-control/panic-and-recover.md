# `panic` y `recover`

`panic` inicia stack unwinding de la goroutine actual y ejecuta deferred functions. `recover` intercepta un panic solo si se usa apropiadamente en una función deferred de esa misma goroutine.

```go
func mustPositive(value int) {
    if value <= 0 {
        panic("value must be positive")
    }
}
```

Panic sirve para invariantes de programación realmente imposibles o algunas fallas de inicialización, no errores normales de input/red/archivo que callers pueden manejar. Las libraries deben evitar panic en condiciones rutinarias.
