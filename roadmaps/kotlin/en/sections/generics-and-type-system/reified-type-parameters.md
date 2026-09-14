# Reified Type Parameters

JVM type erasure normally prevents testing a generic type parameter directly at runtime. An inline function can mark a type parameter `reified`, letting the compiler substitute enough concrete type information for operations such as `is T`, class literals, or reflection helpers.

```kotlin
inline fun <reified T> Any?.isType(): Boolean = this is T

println(value.isType<String>())
```

Reified parameters require inline functions and work best for small generic wrappers. For long-lived runtime type metadata, passing `KClass<T>`, Java `Class<T>`, serializers, or explicit descriptors can be clearer.
