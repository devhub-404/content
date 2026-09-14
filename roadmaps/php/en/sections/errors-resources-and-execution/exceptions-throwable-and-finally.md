# Exceptions, `Throwable`, and `finally`

PHP exceptions and engine errors implement `Throwable`. `try`, multiple `catch` blocks, and `finally` manage exceptional control flow, while custom exception types give callers stable failure categories.

```php
try {
    process($input);
} catch (DomainException $e) {
    report($e);
} finally {
    cleanup();
}
```

Catch only failures you can recover from or translate. Application boundaries may catch broadly for logging and HTTP responses, but lower-level code should not swallow unexpected `Throwable` values and continue with uncertain state.
