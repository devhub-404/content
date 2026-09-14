# Value Classes y Enums

Las value classes envuelven un valor en un tipo distinto y a menudo evitan wrapper allocation, útiles para IDs y units. Los enums modelan un conjunto fijo de constants con properties/methods.

```kotlin
@JvmInline
value class UserId(val value: String)

enum class Status { PENDING, READY, FAILED }
```

Usa value class para type safety sin identidad de objeto, pero entiende que boxing aún puede ocurrir. Usa enum para constants simples y sealed hierarchy cuando las variants lleven datos diferentes.
