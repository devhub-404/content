# Tipos Básicos y Números

Kotlin expone tipos numéricos, Boolean, char, string, arrays y otros con sintaxis uniforme. Los numeric types no hacen widening implícito amplio: convertir `Int` a `Long` es explícito.

```kotlin
val age: Int = 42
val total: Long = 8_000_000_000L
val ratio: Double = 0.75
val enabled: Boolean = true
val letter: Char = 'K' 
```

Elige tipo según rango y API. En JVM, el compiler usa representaciones primitivas cuando puede. El dinero decimal exacto sigue necesitando un tipo como `BigDecimal` en target JVM.
