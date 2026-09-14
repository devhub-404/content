# Lists, Sets, Maps, and Mutability

Kotlin exposes read-only collection interfaces such as `List`, `Set`, and `Map`, plus mutable counterparts. Read-only does not guarantee deep immutability or that no other alias can mutate the same backing collection; it restricts mutation through that reference.

```kotlin
val names: List<String> = listOf("Ada", "Mina")
val mutable = mutableListOf("Ada")
mutable += "Mina"

val counts = mapOf("ready" to 2)
```

Expose read-only interfaces when callers only need observation and mutable collections inside an owner when mutation is required. Choose sets for uniqueness and maps for key/value lookup rather than representing those semantics with lists.
