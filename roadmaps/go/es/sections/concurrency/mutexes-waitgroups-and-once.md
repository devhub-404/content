# Mutexes, WaitGroups y Once

El package `sync` ofrece mutexes, RWMutex, WaitGroups, Once, pools y otras primitivas. Usa un mutex cuando varias goroutines comparten estado mutable y un channel no representa naturalmente transferencia de ownership.

```go
var mu sync.Mutex
var count int

mu.Lock()
count++
mu.Unlock()
```

WaitGroup coordina completion, pero no propaga errores/cancellation por sí mismo. `sync.Once` ejecuta inicialización como máximo una vez. Elige la primitive más simple y no copies valores de sync después de usarlos salvo que su documentación lo permita.
