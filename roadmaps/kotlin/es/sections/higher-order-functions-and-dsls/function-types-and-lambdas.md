# Function Types y Lambdas

Los function types describen callables directamente y las lambdas pueden pasarse, retornarse, almacenarse y capturarse. Kotlin también soporta receiver function types, importantes para DSLs.

```kotlin
val transform: (Int) -> Int = { value -> value * 2 }

fun apply(value: Int, fn: (Int) -> Int): Int = fn(value)
```

Las higher-order functions sirven para policies, callbacks y transforms pequeños. Si el callback lleva estado mutable long-lived o muchas operaciones, una interface/class puede dar un nombre y lifecycle más claros.
