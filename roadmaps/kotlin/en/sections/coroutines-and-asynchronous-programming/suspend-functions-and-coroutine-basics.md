# Suspend Functions and Coroutine Basics

A `suspend` function can suspend without blocking its underlying thread when it calls other suspension points. Suspension is a language/compiler mechanism, while a coroutine library and dispatcher provide the execution environment and scheduling.

```kotlin
suspend fun loadUser(id: Long): User {
    return api.fetchUser(id)
}
```

A suspend function does not automatically run concurrently or on a background thread. Its caller controls the coroutine context. Keep blocking I/O out of CPU-oriented dispatchers and use libraries that provide suspending APIs where possible.
