# Modern Properties and Readonly Design

Modern PHP adds richer object modeling through readonly properties/classes, property hooks, asymmetric visibility, promoted properties, and PHP 8.5 clone-with support. These features let types enforce invariants without boilerplate getters/setters for every field.

```php
final class User
{
    public string $name {
        set => trim($value);
    }

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}
```

Use them to express a stable domain contract, not to make every property magically active. Property access should remain understandable; expensive I/O or broad side effects still belong in explicit methods.
