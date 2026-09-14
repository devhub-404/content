# Reflection and `KClass`

Kotlin reflection exposes `KClass`, callable/property metadata, annotations, type information, and runtime introspection. On JVM, richer Kotlin reflection typically uses the `kotlin-reflect` dependency and can interoperate with Java reflection.

```kotlin
val type = User::class
println(type.simpleName)

for (member in type.members) {
    println(member.name)
}
```

Reflection adds runtime cost and loses some compile-time guarantees. Prefer generated code, serializers, registries, or generics when the set of types is known; use reflection where runtime discovery is genuinely part of the design.
