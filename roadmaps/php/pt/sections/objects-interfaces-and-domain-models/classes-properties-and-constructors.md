# Classes, Properties e Constructors

Classes definem properties, methods, constants, constructors, visibility e inheritance. Constructor property promotion torna data-oriented construction concisa e typed properties checam assignments.

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

Mantenha invariants em methods/constructors em vez de expor tudo mutable. `readonly` restringe reassignment, mas objetos internos mutáveis continuam mutáveis.
