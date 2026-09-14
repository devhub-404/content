# Inheritance, Abstract, Final, and Interfaces

PHP supports single class inheritance and multiple interfaces. Abstract classes can share implementation while requiring members, and `final` prevents extension or overriding. Interfaces define contracts without state implementation.

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

Use inheritance for genuine substitutability and interfaces for capabilities. Composition is often clearer when a class merely depends on another service rather than being a specialized version of it.
