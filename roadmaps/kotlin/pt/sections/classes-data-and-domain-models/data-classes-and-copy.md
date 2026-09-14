# Data Classes e `copy`

Data class gera `equals`, `hashCode`, `toString`, component functions e `copy` a partir das properties do primary constructor. É ideal para DTOs, snapshots e value objects.

```kotlin
data class User(
    val id: Long,
    val name: String
)

val updated = user.copy(name = "Mina")
```

O `copy` é shallow. Objetos mutáveis internos continuam compartilhados. Mantenha no primary constructor o estado que realmente deve participar da equality.
