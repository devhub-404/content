# Functions, Default, Named y Vararg Parameters

Las functions Kotlin pueden tener default values, named arguments, expression bodies, generics y un `vararg`, evitando muchos overloads necesarios en Java.

```kotlin
fun connect(
    host: String,
    port: Int = 443,
    secure: Boolean = true
) { /* ... */ }

connect(host = "example.com", secure = false)
```

Usa named arguments para aclarar booleans o parámetros del mismo tipo, pero recuerda que los callers Java no reciben exactamente la misma ergonomía. Las libraries interoperables necesitan diseño deliberado.
