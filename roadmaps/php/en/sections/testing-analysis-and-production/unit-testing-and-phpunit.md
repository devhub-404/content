# Unit Testing and PHPUnit

PHPUnit is the dominant unit-testing framework in the PHP ecosystem and integrates with Composer, IDEs, coverage tools, and CI. Tests can use data providers, lifecycle hooks, test doubles, attributes, and assertions.

```php
final class CalculatorTest extends TestCase
{
    public function testAdd(): void
    {
        self::assertSame(5, (new Calculator())->add(2, 3));
    }
}
```

Test behavior and domain contracts rather than private implementation. Add integration tests for databases, HTTP, filesystem, serialization, framework routing, and container wiring where mocks cannot prove the real system.
