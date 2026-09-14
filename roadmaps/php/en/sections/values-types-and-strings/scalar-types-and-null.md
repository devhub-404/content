# Scalar Types and `null`

PHP scalar values include integers, floats, strings, and booleans, with `null` representing no value. The runtime is dynamically typed, so a variable name can later hold a value of another type unless a typed property, parameter, return, or other contract restricts it.

```php
$count = 42;
$ratio = 0.75;
$name = 'Mina';
$ready = true;
$missing = null;
```

Do not rely on implicit coercion at trust boundaries. Validate input and convert deliberately. Numeric strings, booleans, null, and empty values have conversion rules that can surprise code written as if PHP were strictly typed everywhere.
