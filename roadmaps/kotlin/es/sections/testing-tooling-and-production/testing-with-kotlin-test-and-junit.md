# Testing con `kotlin.test` y JUnit

Los proyectos Kotlin pueden usar `kotlin.test` como API común de assertions y JUnit en JVM. Multiplatform puede compartir common tests y mantener integration tests específicos.

```kotlin
class CalculatorTest {
    @Test
    fun addsValues() {
        assertEquals(5, Calculator().add(2, 3))
    }
}
```

Prueba comportamiento/contratos, no internals. Las coroutines necesitan soporte de test estructurado para virtual time, dispatchers y cancellation en vez de sleeps.
