# Static Analysis y Coding Standards

PHPStan/Psalm añaden static analysis más allá de runtime types, con generics en annotations, array shapes, nullability y plugins. PSR-12/formatters estandarizan style.

```php
<?php
/** @return list<User> */
function activeUsers(): array {
    // ...
}
```

Adóptalos incrementalmente y reduce el baseline de ignores. Los docblocks valen cuando expresan información que la sintaxis no representa, no para duplicar types obvios.
