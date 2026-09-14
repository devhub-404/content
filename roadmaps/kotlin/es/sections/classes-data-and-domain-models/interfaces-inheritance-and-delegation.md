# Interfaces, Herencia y Delegation

Las classes son final por defecto; `open` es necesario para herencia/override. Las interfaces soportan comportamiento default y delegation con `by` reenvía implementación a otro objeto sin boilerplate.

```kotlin
interface Repository {
    fun save(value: String)
}

class LoggingRepository(
    private val delegate: Repository
) : Repository by delegate
```

Prefiere composición/delegation para reutilización salvo una relación de subtype real. Final-by-default reduce contratos de herencia accidentales.
