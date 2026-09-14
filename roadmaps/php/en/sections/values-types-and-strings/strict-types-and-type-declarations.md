# Strict Types and Type Declarations

PHP supports parameter, return, property, class-constant, and other type declarations. `strict_types=1` changes scalar argument coercion for calls originating from that file, but it does not turn PHP into a globally static language or validate arbitrary external data automatically.

```php
<?php
declare(strict_types=1);

function add(int $a, int $b): int {
    return $a + $b;
}
```

Use type declarations throughout application and library code to make contracts explicit. Static analyzers can refine those contracts further, but runtime input from JSON, HTTP, databases, and arrays still needs validation.
