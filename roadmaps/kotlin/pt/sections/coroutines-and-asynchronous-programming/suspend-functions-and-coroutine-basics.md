# Suspend Functions e Fundamentos de Coroutines

Function `suspend` pode suspender sem bloquear o thread quando chama outros suspension points. Suspension é mecanismo da linguagem/compiler, enquanto coroutine library/dispatcher fornece scheduling.

```kotlin
suspend fun loadUser(id: Long): User {
    return api.fetchUser(id)
}
```

Suspend não significa concorrência nem background thread automaticamente. O caller controla context. Evite I/O bloqueante em dispatchers CPU e prefira APIs suspending.
