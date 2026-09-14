# Attributes y Reflection

Los attributes adjuntan metadata estructurada. Reflection inspecciona classes, methods, properties, types y attributes; los frameworks lo usan para routing, serialización, DI y mapping.

```php
#[Attribute(Attribute::TARGET_CLASS)]
final class Route
{
    public function __construct(public string $path) {}
}

#[Route('/users')]
final class UserController {}
```

Los attributes son pasivos hasta ser interpretados. Reflection cambia visibility/performance por flexibilidad, así que cachea metadata o genera config cuando discovery repetido sea costoso.
