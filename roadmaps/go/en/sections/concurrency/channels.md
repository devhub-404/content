# Channels

Channels are typed synchronization and communication primitives. A send transmits a value, a receive obtains one, and an unbuffered channel synchronizes sender and receiver directly. Buffered channels allow a limited number of sends to proceed before receivers catch up.

```go
jobs := make(chan int)

go func() {
    for job := range jobs {
        process(job)
    }
}()

jobs <- 42
close(jobs)
```

Closing a channel signals that no more values will be sent; receivers can continue draining existing values. The sender side that owns the production lifecycle should normally close the channel. Sending on a closed channel panics, and closing a channel multiple times also panics.
