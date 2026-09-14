# Reflection y `KClass`

Kotlin reflection expone `KClass`, callable/property metadata, annotations y type info. En JVM, reflection más rica suele usar la dependency `kotlin-reflect` e interopera con Java reflection.

```kotlin
val type = User::class
println(type.simpleName)

for (member in type.members) {
    println(member.name)
}
```

Reflection añade runtime cost y pierde garantías. Prefiere generated code, serializers, registries o generics cuando los tipos sean conocidos.
