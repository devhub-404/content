# Enums

PHP enums define a closed set of singleton cases. Backed enums associate each case with a unique `int` or `string` value and support conversion helpers such as `from` and `tryFrom`. Enums can also implement interfaces and define methods.

```php
enum Status: string
{
    case Pending = 'pending';
    case Ready = 'ready';
    case Failed = 'failed';
}
```

Use enums for closed symbolic domain values instead of strings scattered through code. If each alternative needs radically different stored data, a class hierarchy or dedicated value objects may model that better.
