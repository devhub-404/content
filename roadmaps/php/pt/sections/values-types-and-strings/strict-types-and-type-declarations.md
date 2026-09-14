# Strict Types e Declarações de Tipo

PHP suporta types em parameters, return, properties, class constants e outros lugares. `strict_types=1` altera scalar coercion para calls originadas no file, mas não torna PHP static nem valida input externo.

```php
<?php
declare(strict_types=1);

function add(int $a, int $b): int {
    return $a + $b;
}
```

Use declarations para contratos claros e static analysis como complemento. JSON, HTTP, database e arrays ainda precisam validação runtime.
