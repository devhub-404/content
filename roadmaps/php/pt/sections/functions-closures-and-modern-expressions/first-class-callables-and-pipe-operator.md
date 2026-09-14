# First-class Callables e Pipe Operator

First-class callable syntax como `trim(...)` cria callable sem string function name. PHP 8.5 adiciona `|>`, que passa o valor da esquerda para callable à direita, criando pipeline left-to-right.

```php
$slug = ' PHP 8.5 Released '
    |> trim(...)
    |> (fn (string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

Use pipe para transformações lineares. Pipeline longa com side effects/branching pode ficar pior que etapas nomeadas.
