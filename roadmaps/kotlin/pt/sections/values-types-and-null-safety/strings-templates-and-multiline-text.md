# Strings, Templates e Texto Multilinha

Strings Kotlin são imutáveis, suportam templates com `$name`/`${expression}` e raw strings triple-quoted para multilinhas. Helpers como `trimIndent` separam indentação do source da saída.

```kotlin
val name = "Mina"
val message = "Hello, $name!"

val json = """
    {"name":"$name"}
""".trimIndent()
```

Use templates para construção legível, mas encoders estruturados para JSON, SQL, HTML e outras sintaxes onde escaping/injection importam.
