# Forms, Query Strings y Validación

El input web llega como strings, arrays, uploads, headers, cookies y server metadata. Los filter helpers validan formatos seleccionados, pero las reglas de dominio requieren validación explícita.

```php
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);

if ($email === false || $email === null) {
    http_response_code(422);
    exit;
}
```

Valida en el boundary, convierte a domain types y rechaza shapes inesperados. Hidden fields/cookies/session no son automáticamente confiables.
