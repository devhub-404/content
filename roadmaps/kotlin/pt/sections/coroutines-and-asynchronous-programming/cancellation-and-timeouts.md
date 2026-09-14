# Cancellation e Timeouts

Cancellation de coroutine é cooperativo e se propaga por structured scopes. Suspending functions normalmente checam cancellation; loops CPU podem precisar `ensureActive`/`yield`.

```kotlin
withTimeout(5_000) {
    service.load()
}
```

Não engula `CancellationException` como erro comum. Cleanup fica em `finally` e non-cancellable cleanup deve ser curto. Em código de produção, mantenha o lifetime dessas coroutines ligado ao componente ou request que realmente possui o trabalho.
