# Error Reporting y Handlers

Los diagnostics runtime se controlan mediante error reporting y configuración server/app. Los handlers pueden centralizar logging o conversión en boundaries, pero development y production necesitan políticas distintas.

```php
error_reporting(E_ALL);

set_exception_handler(function (Throwable $e): void {
    error_log((string) $e);
    http_response_code(500);
});
```

Registra detalles para operators, no para usuarios web. No expongas stack, SQL, secrets o paths. Alinea framework/server config.
