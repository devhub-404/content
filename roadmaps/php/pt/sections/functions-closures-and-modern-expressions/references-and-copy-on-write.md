# References e Copy-on-write

Values como arrays usam copy-on-write: assignment se comporta como value assignment e engine pode compartilhar storage até mutation. Operador `&` cria aliasing entre variables.

```php
$a = [1, 2, 3];
$b = $a;
$b[] = 4;

$c =& $a;
$c[] = 5;
```

Evite references salvo necessidade real de aliasing/by-reference API. Elas dificultam local reasoning porque assignment pode mudar outro nome.
