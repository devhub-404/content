# Classes, Properties, and Constructors

Classes define properties, methods, constants, constructors, visibility, inheritance, and object behavior. Constructor property promotion makes simple immutable/data-oriented construction concise, while typed properties catch invalid assignments at runtime.

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

Keep domain invariants inside methods and constructors instead of exposing every property as public mutable state. `readonly` is useful for state that should be assigned once after initialization, but nested mutable objects remain mutable.
