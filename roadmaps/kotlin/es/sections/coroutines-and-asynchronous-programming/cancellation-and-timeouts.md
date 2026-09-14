# Cancellation y Timeouts

La cancellation de coroutine es cooperativa y se propaga por structured scopes. Las suspending functions suelen comprobar cancellation; loops CPU pueden necesitar `ensureActive`/`yield`.

```kotlin
withTimeout(5_000) {
    service.load()
}
```

No tragues `CancellationException` como un error normal. El cleanup va en `finally` y el non-cancellable cleanup debe ser breve.
