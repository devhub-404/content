# Versões PHP, Migração e Compatibilidade

Releases adicionam syntax, stdlib, deprecations e behavior changes. Migration guides documentam incompatibilidades e support schedule importa para security.

```php
if (PHP_VERSION_ID < 80500) {
    throw new RuntimeException('PHP 8.5+ required');
}
```

Defina PHP requirement no Composer, teste minimum suportado e CI com deprecations antes de upgrade. Extensions/frameworks também precisam compatibilidade. Automatize essa verificação no CI para que regressions apareçam perto da mudança que as introduziu.
