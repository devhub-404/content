# Type Juggling, Comparações e `match`

PHP possui equality loose (`==`) com coercion e strict (`===`) que compara type/value. Código moderno normalmente prefere strict. `match` também usa comparison estrita e retorna value sem fall-through.

```php
$input = '0';

if ($input === 0) {
    echo 'integer zero';
}

$label = match ($status) {
    Status::Ready => 'ready',
    Status::Failed => 'failed',
};
```

Use loose apenas quando coercion é parte deliberada do contrato. `match` serve a mappings fechados/enums e `if` a regras Boolean independentes.
