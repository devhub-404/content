# Coroutine Scope, `launch` e `async`

Structured concurrency liga lifetime de child coroutines ao parent scope. `launch` inicia trabalho sem value result e `async` produz `Deferred<T>` aguardável.

```kotlin
coroutineScope {
    val user = async { loadUser(id) }
    val orders = async { loadOrders(id) }

    render(user.await(), orders.await())
}
```

Inicie operações independentes antes de await quando quer concorrência. Evite `GlobalScope` porque desconecta lifecycle/failure do owner. Em código de produção, mantenha o lifetime dessas coroutines ligado ao componente ou request que realmente possui o trabalho.
