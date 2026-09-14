# Garbage Collection and Object Lifetimes

Go automatically reclaims unreachable memory, but garbage collection does not close files, cancel goroutines, stop tickers, or release every external resource. Those resources still require explicit lifecycle management, usually with `defer`, `Close`, cancellation, or ownership methods.

```go
type Cache struct {
    data map[string][]byte
}

func (c *Cache) Clear() {
    clear(c.data)
}
```

Memory leaks in managed code are usually accidental reachability: caches, goroutines, maps, global structures, or closures continue referencing data. Use heap/goroutine profiles to understand retention rather than trying to manually control where every object is allocated.
