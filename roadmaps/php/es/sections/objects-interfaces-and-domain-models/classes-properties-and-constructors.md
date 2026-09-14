# Classes, Properties y Constructors

Las classes definen properties, methods, constants, constructors, visibility e inheritance. Constructor property promotion hace concisa la construcción data-oriented y typed properties comprueban assignments.

```php
final class Account
{
    public function __construct(
        public readonly string $owner,
        private int $balance = 0,
    ) {}

    public function balance(): int { return $this->balance; }
}
```

Mantén invariants en methods/constructors en vez de exponer todo mutable. `readonly` restringe reasignación, pero objetos internos mutables siguen siendo mutables.
