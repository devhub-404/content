# Generators y `yield`

Una function con `yield` retorna un `Generator` lazy y conserva estado local. Sirve para files grandes, paginación y pipelines sin arrays completos.

```php
function lines(string $path): Generator {
    $file = fopen($path, 'rb');
    try {
        while (($line = fgets($file)) !== false) {
            yield rtrim($line, "
");
        }
    } finally {
        fclose($file);
    }
}
```

Como la ejecución es lazy, los recursos pueden quedar abiertos hasta terminar. Usa `try/finally` u ownership claro para early termination.
