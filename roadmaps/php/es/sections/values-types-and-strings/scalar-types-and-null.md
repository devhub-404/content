# Tipos Escalares y `null`

Los valores escalares incluyen int, float, string y bool, con `null` para ausencia. El runtime es dynamically typed, por lo que una variable puede recibir otro tipo salvo que un contrato tipado lo restrinja.

```php
$count = 42;
$ratio = 0.75;
$name = 'Mina';
$ready = true;
$missing = null;
```

No dependas de coercion implícita en boundaries. Valida/convierte deliberadamente; numeric strings, booleans, null y empty values tienen reglas sorprendentes.
