# Contraseñas y APIs Criptográficas

PHP ofrece APIs high-level de password hashing/verify con schemes seguros y parámetros en el hash. También ofrece primitivas crypto mediante extensions.

```php
$hash = password_hash($password, PASSWORD_DEFAULT);

if (!password_verify($candidate, $hash)) {
    throw new AuthenticationException();
}
```

Nunca almacenes plaintext ni inventes tu propio hash. Usa `random_bytes`/`random_int` para randomness de seguridad y libraries/protocolos establecidos.
