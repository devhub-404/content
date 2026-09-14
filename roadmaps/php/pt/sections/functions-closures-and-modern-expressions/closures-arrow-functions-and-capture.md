# Closures, Arrow Functions e Capture

Anonymous functions são `Closure` objects. Arrow functions capturam outer variables automaticamente por value; closures tradicionais usam `use` e podem capturar por reference.

```php
$factor = 3;

$multiply = fn (int $value): int => $value * $factor;

$counter = 0;
$next = function () use (&$counter): int {
    return ++$counter;
};
```

Cuidado com reference capture e hidden shared mutation. Para comportamento stateful long-lived, object pode ser mais claro. Em APIs públicas, uma assinatura simples e explícita costuma ser mais fácil de manter que convenções implícitas entre callers.
