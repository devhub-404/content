# Objects y Companion Objects

Un `object` crea un singleton con tipo y una única instancia. Los companion objects asocian members singleton a una class y pueden contener factories, constants o implementar interfaces. Las object expressions crean objetos anónimos locales.

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

El estado singleton es global en el runtime y puede complicar tests/concurrencia. Prefiere ownership explícito cuando el estado varíe por aplicación y usa object para helpers stateless o singletons reales.
