# Garbage Collection e Lifetimes

Go libera memória unreachable automaticamente, mas GC não fecha files, cancela goroutines, para tickers ou libera todo recurso externo. Esses recursos ainda precisam lifecycle explícito com `defer`, `Close`, cancellation ou métodos de ownership.

```go
type Cache struct {
    data map[string][]byte
}

func (c *Cache) Clear() {
    clear(c.data)
}
```

Leaks em código gerenciado geralmente são reachability acidental: caches, goroutines, maps, globals ou closures retêm dados. Use heap/goroutine profiles para entender retenção.
