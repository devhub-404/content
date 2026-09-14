# Unit Testing e PHPUnit

PHPUnit é o framework de unit testing dominante e integra com Composer, IDE, coverage e CI. Suporta data providers, lifecycle, doubles, attributes e assertions.

```php
final class CalculatorTest extends TestCase
{
    public function testAdd(): void
    {
        self::assertSame(5, (new Calculator())->add(2, 3));
    }
}
```

Teste comportamento/contracts, não internals. Use integration tests para database, HTTP, filesystem, serialization e framework wiring. Automatize essa verificação no CI para que regressions apareçam perto da mudança que as introduziu.
