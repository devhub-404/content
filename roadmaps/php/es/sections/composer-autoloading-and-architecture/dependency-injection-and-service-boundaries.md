# Dependency Injection y Service Boundaries

Constructor injection hace explícitas las dependencies y el composition root elige implementations. Los containers automatizan wiring, pero el diseño sigue siendo object construction/dependency direction.

```php
final class ReportService
{
    public function __construct(
        private Clock $clock,
        private ReportRepository $reports,
    ) {}
}
```

No crees una interface para cada class. Defínelas en capabilities que necesiten sustitución o boundary y mantén el domain independiente del container.
