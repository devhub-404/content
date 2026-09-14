# Testing with `kotlin.test` and JUnit

Kotlin projects can use `kotlin.test` as a common assertion API and map to platform test frameworks such as JUnit on JVM. Multiplatform projects can place common tests in shared source sets while keeping platform integration tests separate.

```kotlin
class CalculatorTest {
    @Test
    fun addsValues() {
        assertEquals(5, Calculator().add(2, 3))
    }
}
```

Test behavior and contracts rather than private implementation. Coroutines need structured test support so virtual time, dispatchers, cancellation, and child failures remain deterministic instead of depending on sleeps.
