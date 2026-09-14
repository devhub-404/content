# Memory Model y Data Races

El memory model define cuándo los writes de una goroutine están garantizados para otra. Los accesos conflictivos sin sincronización son data races y vuelven inválido el programa aunque parezca funcionar.

```go
var value int
var ready atomic.Bool

go func() {
    value = 42
    ready.Store(true)
}()

if ready.Load() {
    fmt.Println(value)
}
```

Usa channels, mutexes o atomics para establecer happens-before. El race detector (`-race`) es una herramienta importante, pero solo encuentra races en rutas que se ejecutan.
