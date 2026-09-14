# Enums

Los enums definen un conjunto cerrado de singleton cases. Los backed enums asocian cada case a `int`/`string`, tienen `from`/`tryFrom` y pueden implementar interfaces/methods.

```php
enum Status: string
{
    case Pending = 'pending';
    case Ready = 'ready';
    case Failed = 'failed';
}
```

Usa enums para valores simbólicos cerrados en vez de strings sueltas. Si las variants necesitan datos muy distintos, una hierarchy/value objects puede ser mejor.
