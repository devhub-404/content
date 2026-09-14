# Static Analysis and Coding Standards

Tools such as PHPStan and Psalm add static analysis beyond runtime type declarations, including generic-like annotations, array shapes, nullability, dead-code checks, and framework-specific plugins. PSR-12 and automated formatters standardize source style.

```php
<?php
/** @return list<User> */
function activeUsers(): array {
    // ...
}
```

Use analyzers incrementally and keep a baseline that shrinks rather than becoming a permanent ignore file. Docblock types are most valuable when they express information PHP syntax cannot yet represent, not when they merely duplicate obvious declarations.
