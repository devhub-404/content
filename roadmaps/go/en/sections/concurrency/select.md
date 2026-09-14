# `select` and Multiplexing

`select` waits on multiple channel operations and chooses one that can proceed. It is central to cancellation, fan-in, timeouts, and coordination between concurrent activities. A `default` case makes the select non-blocking.

```go
select {
case value := <-results:
    use(value)
case <-time.After(time.Second):
    return errors.New("timeout")
}
```

When several cases are ready, selection is pseudo-random rather than priority-ordered. Do not use a busy loop around a non-blocking default unless that polling behavior is intentional. Timers and contexts are often better tools for timeouts and cancellation than manually built sleep loops.
