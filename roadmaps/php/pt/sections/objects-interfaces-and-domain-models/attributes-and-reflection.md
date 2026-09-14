# Attributes e Reflection

Attributes anexam metadata estruturada. Reflection inspeciona classes, methods, properties, types e attributes; frameworks usam em routing, serialization, DI e mapping.

```php
#[Attribute(Attribute::TARGET_CLASS)]
final class Route
{
    public function __construct(public string $path) {}
}

#[Route('/users')]
final class UserController {}
```

Attributes são passivos até interpretados. Reflection troca visibility/performance por flexibilidade, então cache metadata ou gere config quando discovery repetido é caro.
