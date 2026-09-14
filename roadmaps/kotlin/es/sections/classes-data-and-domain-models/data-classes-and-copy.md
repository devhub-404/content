# Data Classes y `copy`

Una data class genera `equals`, `hashCode`, `toString`, component functions y `copy` desde las properties del primary constructor. Es ideal para DTOs, snapshots y value objects.

```kotlin
data class User(
    val id: Long,
    val name: String
)

val updated = user.copy(name = "Mina")
```

El `copy` es shallow. Los objetos mutables internos siguen compartidos. Mantén en el primary constructor el estado que realmente deba participar en la equality.
