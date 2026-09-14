# Mutexes, WaitGroups, and Once

The `sync` package provides mutexes, read/write mutexes, WaitGroups, Once, pools, and other synchronization primitives. Use a mutex when several goroutines share mutable state and a channel would not naturally represent the ownership transfer.

```go
var mu sync.Mutex
var count int

mu.Lock()
count++
mu.Unlock()
```

A WaitGroup coordinates completion but does not propagate errors or cancellation by itself. `sync.Once` runs initialization at most once. Choose the simplest primitive matching the invariant, and do not copy synchronization values after they have been used unless their documentation explicitly permits it.
