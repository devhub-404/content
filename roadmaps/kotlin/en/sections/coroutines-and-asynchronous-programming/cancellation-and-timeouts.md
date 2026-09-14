# Cancellation and Timeouts

Coroutine cancellation is cooperative and propagates through structured scopes. Suspending functions in the coroutine library usually check cancellation, while CPU loops may need explicit checks such as `ensureActive` or `yield`.

```kotlin
withTimeout(5_000) {
    service.load()
}
```

Do not swallow `CancellationException` as if it were an ordinary failure. Cleanup belongs in `finally`, and non-cancellable cleanup should be used sparingly because it delays cancellation.
