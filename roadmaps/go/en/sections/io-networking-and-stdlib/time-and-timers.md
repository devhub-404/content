# Time, Timers, and Tickers

The `time` package models instants, durations, parsing/formatting, time zones, timers, and tickers. A `time.Duration` is a typed integer duration, which avoids passing raw milliseconds or seconds without units.

```go
deadline := time.Now().Add(5 * time.Second)

timer := time.NewTimer(time.Second)
defer timer.Stop()

select {
case <-timer.C:
    fmt.Println(deadline)
case <-ctx.Done():
    return ctx.Err()
}
```

Use timers/tickers with clear stop and ownership behavior, especially in long-lived components. Calendar/timezone work is different from measuring elapsed time; `time.Time` carries location/monotonic information according to its operations, so follow the documented comparison and serialization semantics.
