# Functions y Classes Genéricas

Los generics conservan relaciones entre tipos sin casts. Los type parameters pueden tener upper bounds y múltiples constraints, y la inferencia suele derivar argumentos desde la llamada.

```kotlin
class Box<T>(val value: T)

fun <T> first(values: List<T>): T? =
    values.firstOrNull()
```

Usa un type parameter cuando conecte inputs, outputs, receiver o almacenamiento. Si aparece una vez sin relación, una interface o tipo concreto puede ser mejor.
