# Configuration, Secrets, and Environments

Production configuration commonly arrives from environment variables, secret stores, deployment files, or framework configuration. Environment variables are strings and still require parsing, validation, defaults, and clear failure when a required value is absent.

```php
$dsn = getenv('DATABASE_DSN');
if ($dsn === false) {
    throw new RuntimeException('DATABASE_DSN is required');
}
```

Do not commit credentials or production secrets into source repositories. Load configuration near application startup, convert it into typed configuration objects, and pass those objects explicitly so core code does not read global environment state everywhere.
