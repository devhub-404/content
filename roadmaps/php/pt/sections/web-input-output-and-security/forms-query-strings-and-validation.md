# Forms, Query Strings e Validação

Input web chega como strings, arrays, uploads, headers, cookies e server metadata. Filter helpers validam formatos selecionados, mas regras de domínio exigem validação explícita.

```php
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);

if ($email === false || $email === null) {
    http_response_code(422);
    exit;
}
```

Valide na boundary, converta para domain types e rejeite shapes inesperados. Hidden fields/cookies/session não são automaticamente confiáveis.
