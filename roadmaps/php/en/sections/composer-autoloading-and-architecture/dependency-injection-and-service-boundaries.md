# Dependency Injection and Service Boundaries

Constructor injection makes dependencies visible and lets application composition choose concrete implementations for interfaces. Framework containers can automate wiring, but the underlying design is still ordinary object construction and dependency direction.

```php
final class ReportService
{
    public function __construct(
        private Clock $clock,
        private ReportRepository $reports,
    ) {}
}
```

Do not create an interface for every class automatically. Define interfaces around capabilities that need substitution, multiple implementations, or architectural boundaries. Keep the domain independent from framework container APIs where practical.
