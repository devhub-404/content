# Attributes and Reflection

Attributes attach structured metadata to declarations. Reflection APIs can inspect classes, methods, properties, types, attributes, and invoke or construct dynamically; frameworks use these capabilities for routing, serialization, dependency injection, testing, and mapping.

```php
#[Attribute(Attribute::TARGET_CLASS)]
final class Route
{
    public function __construct(public string $path) {}
}

#[Route('/users')]
final class UserController {}
```

Attributes are passive until code interprets them. Reflection gives flexibility at the cost of compile-time visibility and performance, so cache metadata or use generated configuration where repeated runtime discovery is expensive.
