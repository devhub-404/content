# Lists, Sets, Maps y Mutability

Kotlin ofrece interfaces read-only `List`, `Set`, `Map` y contrapartes mutables. Read-only no garantiza deep immutability ni ausencia de otros aliases mutables; solo restringe esa referencia.

```kotlin
val names: List<String> = listOf("Ada", "Mina")
val mutable = mutableListOf("Ada")
mutable += "Mina"

val counts = mapOf("ready" to 2)
```

Expón interfaces read-only cuando los callers solo observan y collections mutables dentro del owner cuando necesites mutation. Usa set para unicidad y map para lookup.
