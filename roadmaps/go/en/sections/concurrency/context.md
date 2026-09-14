# `context` for Cancellation and Deadlines

`context.Context` carries cancellation, deadlines, and request-scoped values across API boundaries. Long-running I/O and request work should accept a context when callers need to cancel or impose a deadline.

```go
func load(ctx context.Context) error {
    req, err := http.NewRequestWithContext(
        ctx,
        http.MethodGet,
        endpoint,
        nil,
    )
    if err != nil {
        return err
    }

    _, err = http.DefaultClient.Do(req)
    return err
}
```

Pass contexts explicitly as the first parameter rather than storing them in structs for later unrelated use. Do not put ordinary optional parameters into context; values are for request-scoped metadata that must cross process/API boundaries. Always call a returned cancel function when the API requires it.
