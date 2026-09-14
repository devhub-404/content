# Objects and Companion Objects

An `object` declaration creates a singleton with a type and one instance. Companion objects associate singleton members with a class and can implement interfaces, hold factories, constants, or metadata. Object expressions create anonymous objects for local one-off implementations.

```kotlin
object IdGenerator {
    private var next = 0L
    fun nextId(): Long = ++next
}

class User {
    companion object {
        fun guest() = User()
    }
}
```

Singleton state is globally shared within its runtime context and can complicate tests or concurrency. Prefer dependency injection or explicit ownership when state varies by application instance; use objects for genuinely process-wide stateless helpers or stable singletons.
