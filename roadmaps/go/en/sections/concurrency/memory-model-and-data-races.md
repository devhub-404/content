# Memory Model and Data Races

The Go memory model defines when one goroutine's writes are guaranteed to be observed by another. Unsynchronized conflicting memory accesses are data races and make program behavior invalid even if the code appears to work in tests.

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

Use channels, mutexes, or atomic operations to establish the required happens-before relationships. The race detector (`go test -race`, `go run -race`) is an important development tool, but it can only report races on execution paths that actually run.
