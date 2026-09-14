# Herencia, Abstract, Final e Interfaces

PHP soporta herencia simple de classes y múltiples interfaces. Las abstract classes comparten implementación, `final` impide extensión/override y las interfaces definen contracts.

```php
interface Clock
{
    public function now(): DateTimeImmutable;
}

abstract class BaseService
{
    abstract public function run(): void;
}

final class Service extends BaseService implements Clock
{
    // ...
}
```

Usa herencia para sustitución e interfaces para capacidades. Composición es mejor cuando una class solo depende de otro service.
