# `panic` and `recover`

`panic` begins stack unwinding in the current goroutine, running deferred functions along the way. `recover` can intercept a panic only when called appropriately from a deferred function in that panicking goroutine.

```go
func mustPositive(value int) {
    if value <= 0 {
        panic("value must be positive")
    }
}
```

Panic is appropriate for truly unrecoverable programmer invariants or some initialization failures, not ordinary input, network, or file errors that callers can reasonably handle. Libraries should be very cautious about allowing panics to escape for routine error conditions.
