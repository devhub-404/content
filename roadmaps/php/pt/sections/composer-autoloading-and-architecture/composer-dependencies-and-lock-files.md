# Dependencies Composer e Lock Files

`composer.json` declara metadata/constraints e `composer.lock` registra grafo resolvido para installs reproduzíveis. Libraries publicam constraints em vez de impor lock do próprio repo ao consumer.

```json
{
  "require": {
    "php": "^8.5",
    "psr/log": "^3.0"
  }
}
```

Revise transitivas, PHP/extensions requirements, security e abandoned packages. Deploy use `composer install` com lockfile versionado.
