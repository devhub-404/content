# Tipos Escalares e `null`

Valores escalares incluem int, float, string e bool, com `null` para ausência. Runtime é dynamically typed, então variável pode receber outro tipo salvo quando um contrato tipado restringe.

```php
$count = 42;
$ratio = 0.75;
$name = 'Mina';
$ready = true;
$missing = null;
```

Não dependa de coercion implícita em boundaries. Valide/converta deliberadamente; numeric strings, booleans, null e empty values têm regras surpreendentes.
