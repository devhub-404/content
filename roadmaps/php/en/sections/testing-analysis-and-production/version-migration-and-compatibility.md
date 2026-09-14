# PHP Versions, Migration, and Compatibility

PHP releases add syntax, standard-library features, deprecations, and behavior changes. Migration guides document backward-incompatible changes and deprecations between minor release lines, and supported-version schedules matter for security updates.

```php
if (PHP_VERSION_ID < 80500) {
    throw new RuntimeException('PHP 8.5+ required');
}
```

Set an explicit PHP requirement in Composer, test the oldest version you claim to support, and run deprecation-aware CI before upgrading. Extensions and framework versions also need compatible binaries and APIs, not just the core interpreter.
