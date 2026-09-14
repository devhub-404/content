# Closures, Arrow Functions, and Capture

Anonymous functions are `Closure` objects. Arrow functions capture referenced outer variables automatically by value, while traditional closures use a `use` clause and can explicitly capture by reference.

```php
$factor = 3;

$multiply = fn (int $value): int => $value * $factor;

$counter = 0;
$next = function () use (&$counter): int {
    return ++$counter;
};
```

Be careful with reference capture because hidden shared mutation can make callbacks difficult to reason about. For long-lived stateful behavior, an object with explicit fields and methods can be clearer than a closure mutating external variables.
