# Goroutines

A goroutine is a concurrently executing Go function managed by the runtime. Starting one with `go` is cheap compared with creating an operating-system thread directly, but every goroutine still needs a lifetime, a way to finish, and an ownership story for the data it accesses.

```go
go func() {
    result := doWork()
    results <- result
}()
```

Do not launch goroutines without knowing how they stop. Leaked goroutines retain stacks, references, timers, sockets, or other resources. Structured application code usually ties goroutine lifetime to a request, context, worker group, or owning component.
