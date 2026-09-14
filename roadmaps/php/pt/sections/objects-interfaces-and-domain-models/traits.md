# Traits

Traits fornecem reuso horizontal inserindo methods/properties em classes sem subtype relationship. Há syntax de conflict resolution para nomes iguais.

```php
trait LogsActions
{
    private function log(string $message): void
    {
        error_log($message);
    }
}

final class Service
{
    use LogsActions;
}
```

Traits servem a mechanics coesas pequenas, mas traits stateful grandes escondem dependencies. Prefira composition para behavior com lifecycle/collaborators próprios. Use esse mecanismo quando ele reduz duplicação sem esconder relações importantes entre tipos e comportamento.
