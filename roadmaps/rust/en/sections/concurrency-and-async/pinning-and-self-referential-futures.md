# Pinning and Self-referential Futures

`Pin<P>` expresses that the pointee must not be moved in ways that would violate invariants. Async state machines and some self-referential structures rely on pinning because internal references can become invalid if the state machine moves after being polled.

```rust
use std::pin::Pin;
use std::future::Future;

fn poll_later(
    future: Pin<&mut dyn Future<Output = ()>>
) {
    // an executor may poll this pinned future
}
```

Most async application code does not manipulate `Pin` manually because executors, `Box::pin`, and generated async machinery hide the details. Learn the concept so advanced Future implementations and compiler errors make sense, but do not introduce pinning unless your abstraction truly needs immovability guarantees.
