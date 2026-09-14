# Interfaces, Inheritance, and Delegation

Kotlin classes are final by default; a class or method must be `open` to allow ordinary inheritance/overriding. Interfaces support abstract and default behavior, and delegation with `by` can forward an interface implementation to another object without boilerplate.

```kotlin
interface Repository {
    fun save(value: String)
}

class LoggingRepository(
    private val delegate: Repository
) : Repository by delegate
```

Prefer composition and delegation for behavior reuse unless the subtype relationship is genuine. Final-by-default design reduces accidental inheritance contracts and makes library evolution safer.
