# Type Juggling, Comparisons, and `match`

PHP has both loose equality (`==`) with coercion rules and strict identity-style comparison (`===`) that compares type and value. Modern application code usually prefers strict comparisons to avoid surprising conversions. `match` also uses strict comparison and returns a value without switch-style fall-through.

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

Use loose comparison only when coercion is a deliberate part of the contract. `match` works well for closed mappings and enum states, while ordinary `if` remains clearer for ranges and independent Boolean rules.
