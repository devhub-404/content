# Error Reporting and Handlers

PHP runtime diagnostics are controlled by error-reporting settings and application/server configuration. Error and exception handlers can centralize logging or conversion at process/request boundaries, but development and production display policies should differ.

```php
error_reporting(E_ALL);

set_exception_handler(function (Throwable $e): void {
    error_log((string) $e);
    http_response_code(500);
});
```

Log detailed diagnostics where operators can access them, but do not display stack traces, SQL, secrets, or filesystem details to untrusted web users. Keep framework and server logging configuration aligned with the application policy.
