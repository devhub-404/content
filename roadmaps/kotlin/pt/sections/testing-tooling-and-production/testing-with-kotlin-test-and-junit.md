# Testes com `kotlin.test` e JUnit

Projetos Kotlin podem usar `kotlin.test` como API comum de assertions e JUnit no JVM. Multiplatform pode compartilhar common tests e manter integration tests específicos.

```kotlin
class CalculatorTest {
    @Test
    fun addsValues() {
        assertEquals(5, Calculator().add(2, 3))
    }
}
```

Teste comportamento/contratos, não internals. Coroutines precisam de suporte de teste estruturado para virtual time, dispatchers e cancellation em vez de sleeps.
