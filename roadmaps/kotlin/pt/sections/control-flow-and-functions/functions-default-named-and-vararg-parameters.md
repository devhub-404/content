# Functions, Default, Named e Vararg Parameters

Functions Kotlin podem ter default values, named arguments, expression bodies, generics e um `vararg`, evitando muitos overloads necessários em Java.

```kotlin
fun connect(
    host: String,
    port: Int = 443,
    secure: Boolean = true
) { /* ... */ }

connect(host = "example.com", secure = false)
```

Use named arguments para esclarecer booleans ou parâmetros de mesmo tipo, mas lembre que Java callers não recebem exatamente a mesma ergonomia. Libraries interop precisam design deliberado.
