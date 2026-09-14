# API Design and Small Interfaces

Idiomatic Go APIs tend to accept behavior through small interfaces and return concrete types. This keeps the producer free to expose useful concrete methods while consumers depend only on the capability they need.

```go
type Clock interface {
    Now() time.Time
}

func NewService(clock Clock) *Service {
    return &Service{clock: clock}
}
```

Avoid defining interfaces preemptively next to every implementation. Often the consumer should define the interface when substitution is needed. Prefer zero-value usefulness, clear error contracts, explicit contexts, and simple structs over deep abstraction layers.
