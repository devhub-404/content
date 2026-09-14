# Coroutine Scope, `launch` y `async`

Structured concurrency liga el lifetime de child coroutines al parent scope. `launch` inicia trabajo sin value result y `async` produce un `Deferred<T>` awaitable.

```kotlin
coroutineScope {
    val user = async { loadUser(id) }
    val orders = async { loadOrders(id) }

    render(user.await(), orders.await())
}
```

Inicia operaciones independientes antes de await cuando quieras concurrencia. Evita `GlobalScope` porque desconecta lifecycle/failure del owner.
