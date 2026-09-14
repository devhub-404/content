# Type Juggling, Comparaciones y `match`

PHP tiene igualdad loose (`==`) con coercion y strict (`===`) que compara type/value. El código moderno suele preferir strict. `match` también usa comparación estricta y retorna un value sin fall-through.

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

Usa loose solo cuando la coerción sea parte deliberada del contrato. `match` sirve para mappings cerrados/enums e `if` para reglas Boolean independientes.
