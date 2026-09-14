# Unit Testing y PHPUnit

PHPUnit es el framework de unit testing dominante e integra con Composer, IDE, coverage y CI. Soporta data providers, lifecycle, doubles, attributes y assertions.

```php
final class CalculatorTest extends TestCase
{
    public function testAdd(): void
    {
        self::assertSame(5, (new Calculator())->add(2, 3));
    }
}
```

Prueba comportamiento/contracts, no internals. Usa integration tests para database, HTTP, filesystem, serialización y framework wiring. Automatiza esta comprobación en CI para que las regressions aparezcan cerca del cambio que las introdujo.
