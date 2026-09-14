# Dependencies Composer y Lock Files

`composer.json` declara metadata/constraints y `composer.lock` registra el grafo resuelto para installs reproducibles. Las libraries publican constraints en vez de imponer su lockfile al consumer.

```json
{
  "require": {
    "php": "^8.5",
    "psr/log": "^3.0"
  }
}
```

Revisa transitivas, requisitos PHP/extensions, seguridad y abandoned packages. El deploy debería usar `composer install` con lockfile versionado.
