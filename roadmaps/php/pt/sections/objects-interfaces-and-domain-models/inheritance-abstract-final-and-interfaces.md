# Herança, Abstract, Final e Interfaces

PHP suporta herança simples de classes e múltiplas interfaces. Abstract classes compartilham implementação, `final` impede extensão/override e interfaces definem contracts.

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

Use herança para substituibilidade e interfaces para capacidades. Composição é melhor quando class apenas depende de outro service. Use esse mecanismo quando ele reduz duplicação sem esconder relações importantes entre tipos e comportamento.
