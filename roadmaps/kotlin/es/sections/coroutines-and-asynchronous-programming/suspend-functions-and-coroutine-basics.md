# Suspend Functions y Fundamentos de Coroutines

Una function `suspend` puede suspender sin bloquear el thread cuando llama a otros suspension points. Suspension es un mecanismo del lenguaje/compiler, mientras la coroutine library/dispatcher aporta scheduling.

```kotlin
suspend fun loadUser(id: Long): User {
    return api.fetchUser(id)
}
```

Suspend no significa concurrencia ni background thread automáticamente. El caller controla el context. Evita I/O bloqueante en dispatchers CPU y prefiere APIs suspending.
