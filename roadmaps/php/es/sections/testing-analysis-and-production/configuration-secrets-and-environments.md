# Configuración, Secrets y Environments

La configuración suele llegar de env vars, secret stores, deploy files o frameworks. Las env vars son strings y necesitan parsing/validation/defaults.

```php
$dsn = getenv('DATABASE_DSN');
if ($dsn === false) {
    throw new RuntimeException('DATABASE_DSN is required');
}
```

No versiones secrets. Carga config al startup, conviértela en typed config objects y pásala explícitamente para evitar lectura global dispersa.
