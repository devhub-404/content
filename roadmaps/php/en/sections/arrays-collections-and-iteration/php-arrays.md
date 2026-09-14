# PHP Arrays

A PHP array is an ordered map, so the same built-in type represents list-like sequences, associative dictionaries, and mixtures of integer/string keys. This flexibility is convenient but can make data shapes ambiguous in large systems.

```php
$list = ['a', 'b', 'c'];
$map = ['name' => 'Mina', 'active' => true];

$list[] = 'd';
$map['role'] = 'admin';
```

Use array shapes deliberately at boundaries and prefer objects, enums, or dedicated collection/value types when a structure has a stable domain meaning. Functions such as `array_is_list` help distinguish list-like arrays when it matters.
