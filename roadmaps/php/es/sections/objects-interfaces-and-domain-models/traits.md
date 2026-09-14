# Traits

Los traits ofrecen reutilización horizontal insertando methods/properties en classes sin relación de subtype. Hay sintaxis de conflict resolution para nombres iguales.

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

Los traits sirven para mechanics cohesionadas pequeñas, pero traits stateful grandes esconden dependencies. Prefiere composición para behavior con lifecycle/collaborators propios. Usa este mecanismo cuando reduzca duplicación sin ocultar relaciones importantes entre tipos y comportamiento.
