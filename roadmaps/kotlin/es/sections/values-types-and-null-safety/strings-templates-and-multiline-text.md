# Strings, Templates y Texto Multilínea

Las strings de Kotlin son inmutables, soportan templates con `$name`/`${expression}` y raw strings triple-quoted para multilínea. Helpers como `trimIndent` separan la indentación del source de la salida.

```kotlin
val name = "Mina"
val message = "Hello, $name!"

val json = """
    {"name":"$name"}
""".trimIndent()
```

Usa templates para construcción legible, pero encoders estructurados para JSON, SQL, HTML y otras sintaxis donde escaping/injection importen.
