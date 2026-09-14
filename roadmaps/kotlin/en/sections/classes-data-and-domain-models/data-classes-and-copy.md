# Data Classes and `copy`

A data class generates value-oriented `equals`, `hashCode`, `toString`, component functions, and `copy` from properties in its primary constructor. It is ideal for DTOs, immutable state snapshots, and domain values whose identity is their data.

```kotlin
data class User(
    val id: Long,
    val name: String
)

val updated = user.copy(name = "Mina")
```

The generated copy is shallow. Mutable objects stored inside the data class remain shared unless you copy them separately. Keep primary-constructor properties aligned with the state that should participate in equality.
