# Arrays PHP

Un array PHP es un ordered map y representa listas, diccionarios asociativos y mezclas de keys int/string. La flexibilidad es útil, pero puede volver ambiguos los shapes.

```php
$list = ['a', 'b', 'c'];
$map = ['name' => 'Mina', 'active' => true];

$list[] = 'd';
$map['role'] = 'admin';
```

Usa arrays deliberadamente y prefiere objects/value types cuando la estructura tenga significado estable. `array_is_list` ayuda a distinguir arrays tipo lista.
