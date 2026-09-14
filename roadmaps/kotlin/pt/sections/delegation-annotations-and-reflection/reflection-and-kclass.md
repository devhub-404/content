# Reflection e `KClass`

Kotlin reflection expõe `KClass`, callable/property metadata, annotations e type info. Na JVM, reflection mais rica normalmente usa dependency `kotlin-reflect` e interoperates com Java reflection.

```kotlin
val type = User::class
println(type.simpleName)

for (member in type.members) {
    println(member.name)
}
```

Reflection adiciona runtime cost e perde garantias. Prefira generated code, serializers, registries ou generics quando tipos são conhecidos.
