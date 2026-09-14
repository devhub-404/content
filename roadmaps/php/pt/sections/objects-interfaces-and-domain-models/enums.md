# Enums

Enums definem conjunto fechado de singleton cases. Backed enums associam cada case a `int`/`string`, têm `from`/`tryFrom` e podem implementar interfaces/methods.

```php
enum Status: string
{
    case Pending = 'pending';
    case Ready = 'ready';
    case Failed = 'failed';
}
```

Use enums para valores simbólicos fechados em vez de strings soltas. Se variants precisam dados muito diferentes, hierarchy/value objects podem ser melhores.
