# Dependency Injection e Service Boundaries

Constructor injection deixa dependencies explícitas e composition root escolhe implementations. Containers automatizam wiring, mas o design continua object construction/dependency direction.

```php
final class ReportService
{
    public function __construct(
        private Clock $clock,
        private ReportRepository $reports,
    ) {}
}
```

Não crie interface para toda class. Defina em capabilities que precisam substituição ou boundary e mantenha domain independente do container.
