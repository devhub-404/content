# Dispatchers and Coroutine Context

Coroutine context carries dispatcher, job, name, and other elements. Dispatchers decide where coroutine code runs: CPU-oriented pools, I/O-oriented pools, main/UI threads, or custom execution contexts depending on platform.

```kotlin
withContext(Dispatchers.IO) {
    Files.readString(path)
}
```

Switch context for blocking or platform-constrained work intentionally, not around every function. Libraries should generally expose suspending operations without hard-coding caller dispatchers unless they own genuinely blocking implementation details.
