# Traits

Traits provide horizontal code reuse by inserting methods and properties into classes without establishing a subtype relationship. Conflict-resolution syntax handles methods with the same name from several traits.

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

Traits are useful for small cohesive implementation mechanics, but large stateful traits can hide dependencies and create tight coupling. Prefer services/composition when behavior has its own lifecycle or collaborators.
