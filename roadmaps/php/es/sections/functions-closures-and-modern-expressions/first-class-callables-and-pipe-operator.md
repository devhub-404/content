# First-class Callables y Pipe Operator

First-class callable syntax como `trim(...)` crea un callable sin string function name. PHP 8.5 añade `|>`, que pasa el valor izquierdo a un callable a la derecha, creando un pipeline left-to-right.

```php
$slug = ' PHP 8.5 Released '
    |> trim(...)
    |> (fn (string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

Usa pipe para transformaciones lineales. Un pipeline largo con side effects/branching puede ser peor que etapas nombradas.
