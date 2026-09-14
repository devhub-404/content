# Strings, Templates, and Multiline Text

Kotlin strings are immutable, support template interpolation with `$name` and `${expression}`, and provide triple-quoted raw strings for multiline text. Raw strings keep characters largely literal, while helpers such as `trimIndent` make source indentation independent from output indentation.

```kotlin
val name = "Mina"
val message = "Hello, $name!"

val json = """
    {"name":"$name"}
""".trimIndent()
```

Use string templates for readable construction, but use structured encoders for JSON, SQL, HTML, and other syntaxes where escaping and injection rules matter. On JVM, string representation follows the underlying platform.
