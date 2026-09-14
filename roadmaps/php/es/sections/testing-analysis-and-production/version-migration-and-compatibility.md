# Versiones PHP, Migración y Compatibilidad

Las releases añaden sintaxis, stdlib, deprecations y behavior changes. Las migration guides documentan incompatibilidades y el support schedule importa para security.

```php
if (PHP_VERSION_ID < 80500) {
    throw new RuntimeException('PHP 8.5+ required');
}
```

Define el PHP requirement en Composer, prueba el mínimo soportado y CI con deprecations antes del upgrade. Extensions/frameworks también necesitan compatibilidad.
