# `defer` and Cleanup

A `defer` statement schedules a function call to run when the surrounding function returns. Deferred calls execute in last-in-first-out order, and their arguments are evaluated when the defer statement executes.

```go
file, err := os.Open(path)
if err != nil {
    return err
}
defer file.Close()

// use file
```

`defer` makes cleanup sit next to successful acquisition and works across early returns, which is one of Go's main resource-management idioms. Keep long-lived resources in appropriately small function scopes so deferred cleanup happens when you actually want it, not much later.
