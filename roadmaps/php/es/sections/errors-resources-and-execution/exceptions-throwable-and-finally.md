# Exceptions, `Throwable` y `finally`

Las exceptions y engine errors implementan `Throwable`. `try`/`catch`/`finally` manejan flow y las custom exceptions dan categorías estables.

```php
try {
    process($input);
} catch (DomainException $e) {
    report($e);
} finally {
    cleanup();
}
```

Captura solo fallos recuperables/traducibles. Los boundaries pueden hacer catch broad para logging/HTTP, pero low-level code no debe tragarse errores inesperados.
