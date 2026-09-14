# Senhas e APIs Criptográficas

PHP fornece APIs high-level de password hashing/verify com schemes seguros e parâmetros no hash. Também possui primitives crypto por extensions.

```php
$hash = password_hash($password, PASSWORD_DEFAULT);

if (!password_verify($candidate, $hash)) {
    throw new AuthenticationException();
}
```

Nunca armazene plaintext nem invente hash próprio. Use `random_bytes`/`random_int` para randomness de segurança e libraries/protocols estabelecidos. Dados externos continuam não confiáveis mesmo depois de chegar por uma API conveniente da linguagem.
