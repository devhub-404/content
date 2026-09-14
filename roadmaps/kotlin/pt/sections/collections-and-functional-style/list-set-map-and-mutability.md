# Lists, Sets, Maps e Mutability

Kotlin oferece interfaces read-only `List`, `Set`, `Map` e counterparts mutáveis. Read-only não garante deep immutability nem ausência de outros aliases mutáveis; apenas restringe aquela referência.

```kotlin
val names: List<String> = listOf("Ada", "Mina")
val mutable = mutableListOf("Ada")
mutable += "Mina"

val counts = mapOf("ready" to 2)
```

Exponha interfaces read-only quando callers só observam e collections mutáveis dentro do owner quando precisa mutation. Use set para unicidade e map para lookup.
