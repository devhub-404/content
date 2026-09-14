# Error Reporting e Handlers

Diagnostics runtime são controlados por error reporting e server/app config. Handlers podem centralizar logging ou conversão em boundaries, mas development e production precisam policies diferentes.

```php
error_reporting(E_ALL);

set_exception_handler(function (Throwable $e): void {
    error_log((string) $e);
    http_response_code(500);
});
```

Logue detalhes para operators, não para usuários web. Não exponha stack, SQL, secrets ou paths. Alinhe framework/server config.
