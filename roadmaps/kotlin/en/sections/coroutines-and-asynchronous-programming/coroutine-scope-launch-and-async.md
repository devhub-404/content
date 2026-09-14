# Coroutine Scope, `launch`, and `async`

Structured concurrency ties child coroutine lifetimes to a parent scope. `launch` starts work with no result value beyond completion, while `async` produces a `Deferred<T>` that can be awaited for a value.

```kotlin
coroutineScope {
    val user = async { loadUser(id) }
    val orders = async { loadOrders(id) }

    render(user.await(), orders.await())
}
```

Start independent operations before awaiting them when true concurrency is desired. Avoid `GlobalScope` for ordinary application work because it disconnects child lifetime and failure from the owner that should cancel or observe it.
