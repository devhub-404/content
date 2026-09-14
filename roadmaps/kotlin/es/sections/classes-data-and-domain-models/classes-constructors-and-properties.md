# Classes, Constructors y Properties

Los primary constructor parameters viven en el header y se vuelven properties con `val`/`var`. Secondary constructors, init blocks, accessors y backing fields cubren inicialización más compleja.

```kotlin
class Account(
    val owner: String,
    initialBalance: Long = 0
) {
    var balance: Long = initialBalance
        private set
}
```

Mantén invariantes dentro del tipo en vez de exponer todo mutable. Las properties son abstracciones del lenguaje, no simples fields públicos.
