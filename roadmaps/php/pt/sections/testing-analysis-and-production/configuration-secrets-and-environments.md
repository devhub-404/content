# Configuração, Secrets e Environments

Config normalmente chega de env vars, secret stores, deploy files ou framework. Env vars são strings e precisam parsing/validation/defaults.

```php
$dsn = getenv('DATABASE_DSN');
if ($dsn === false) {
    throw new RuntimeException('DATABASE_DSN is required');
}
```

Não version secrets. Carregue config no startup, converta em typed config objects e passe explicitamente para evitar leitura global espalhada.
