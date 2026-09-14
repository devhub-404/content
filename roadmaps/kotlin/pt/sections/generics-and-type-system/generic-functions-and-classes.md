# Functions e Classes Genéricas

Generics preservam relações entre tipos sem casts. Type parameters podem ter upper bounds e múltiplas constraints, e inference normalmente deriva argumentos da chamada.

```kotlin
class Box<T>(val value: T)

fun <T> first(values: List<T>): T? =
    values.firstOrNull()
```

Use type parameter quando conecta inputs, outputs, receiver ou storage. Se aparece uma vez sem relação, interface ou tipo concreto pode ser melhor.
