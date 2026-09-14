# Garbage Collection y Lifetimes

Go libera memoria unreachable automáticamente, pero el GC no cierra files, cancela goroutines, detiene tickers ni libera todo recurso externo. Esos recursos aún necesitan lifecycle explícito mediante `defer`, `Close`, cancellation o métodos de ownership.

```go
type Cache struct {
    data map[string][]byte
}

func (c *Cache) Clear() {
    clear(c.data)
}
```

Los leaks en código gestionado suelen ser reachability accidental: caches, goroutines, maps, globals o closures retienen datos. Usa heap/goroutine profiles para entender la retención.
