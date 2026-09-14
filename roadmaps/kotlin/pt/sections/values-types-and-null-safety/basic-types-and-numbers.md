# Tipos Básicos e Números

Kotlin expõe tipos numéricos, Boolean, char, string, arrays e outros com sintaxe uniforme. Numeric types não fazem widening implícito amplo: converter `Int` para `Long` é explícito.

```kotlin
val age: Int = 42
val total: Long = 8_000_000_000L
val ratio: Double = 0.75
val enabled: Boolean = true
val letter: Char = 'K' 
```

Escolha tipo por range e API. Na JVM, o compiler usa representations primitivas quando possível. Dinheiro decimal exato ainda precisa de tipo como `BigDecimal` no target JVM.
