# Closures, Arrow Functions y Capture

Las anonymous functions son `Closure` objects. Las arrow functions capturan outer variables automáticamente por value; closures tradicionales usan `use` y pueden capturar por reference.

```php
$factor = 3;

$multiply = fn (int $value): int => $value * $factor;

$counter = 0;
$next = function () use (&$counter): int {
    return ++$counter;
};
```

Cuidado con reference capture y hidden shared mutation. Para comportamiento stateful long-lived, un objeto puede ser más claro.
