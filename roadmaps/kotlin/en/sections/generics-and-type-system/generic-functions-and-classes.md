# Generic Functions and Classes

Generics let functions, classes, and interfaces preserve relationships between types without casts. Type parameters can have upper bounds and multiple constraints, while inference often derives arguments from the call site.

```kotlin
class Box<T>(val value: T)

fun <T> first(values: List<T>): T? =
    values.firstOrNull()
```

Use a type parameter when it connects inputs, outputs, receivers, or stored data. If the parameter appears only once and does not preserve a relationship, an interface or concrete type may communicate the API better.
