# Strict Types y Declaraciones de Tipo

PHP soporta types en parameters, return, properties, class constants y otros lugares. `strict_types=1` cambia scalar coercion para calls originadas en ese file, pero no vuelve PHP estático ni valida input externo.

```php
<?php
declare(strict_types=1);

function add(int $a, int $b): int {
    return $a + $b;
}
```

Usa declarations para contratos claros y static analysis como complemento. JSON, HTTP, database y arrays aún necesitan validación runtime.
