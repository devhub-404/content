# Exceptions, `Throwable` e `finally`

Exceptions e engine errors implementam `Throwable`. `try`/`catch`/`finally` tratam flow e custom exceptions dão categories estáveis.

```php
try {
    process($input);
} catch (DomainException $e) {
    report($e);
} finally {
    cleanup();
}
```

Capture apenas falhas recuperáveis/traduzíveis. Boundaries podem catch broad para logging/HTTP, mas low-level code não deve engolir unexpected errors. Mantenha cleanup e tratamento de falhas próximos da operação que adquiriu ou abriu o recurso.
