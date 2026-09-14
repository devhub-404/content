# Arrays PHP

Array PHP é ordered map e representa listas, dictionaries associativos e misturas de keys int/string. A flexibilidade é útil, mas pode tornar shapes ambíguos.

```php
$list = ['a', 'b', 'c'];
$map = ['name' => 'Mina', 'active' => true];

$list[] = 'd';
$map['role'] = 'admin';
```

Use arrays deliberadamente e prefira objects/value types quando estrutura tem significado estável. `array_is_list` ajuda a distinguir list-like arrays.
