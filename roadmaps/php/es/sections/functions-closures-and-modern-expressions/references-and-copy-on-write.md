# References y Copy-on-write

Values como arrays usan copy-on-write: assignment se comporta como value assignment y el engine puede compartir storage hasta mutation. El operador `&` crea aliasing entre variables.

```php
$a = [1, 2, 3];
$b = $a;
$b[] = 4;

$c =& $a;
$c[] = 5;
```

Evita references salvo necesidad real de aliasing/by-reference API. Dificultan el razonamiento local porque un assignment puede cambiar otro nombre.
