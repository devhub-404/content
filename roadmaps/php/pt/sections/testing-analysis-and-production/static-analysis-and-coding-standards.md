# Static Analysis e Coding Standards

PHPStan/Psalm adicionam static analysis além dos runtime types, com generics em annotations, array shapes, nullability e plugins. PSR-12/formatters padronizam style.

```php
<?php
/** @return list<User> */
function activeUsers(): array {
    // ...
}
```

Adote incrementalmente e reduza baseline de ignores. Docblocks valem quando expressam informação que syntax não representa, não para duplicar types óbvios.
