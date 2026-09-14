# O que é PHP

PHP é uma linguagem dinamicamente tipada de propósito geral com forte uso web, mas também executa CLI, workers, daemons e tooling. Em deploy comum, o código roda por request via PHP-FPM ou integração de server, embora runtimes modernos também mantenham workers vivos.

```php
<?php
$name = 'Mina';
echo "Hello, {$name}!
";
```

Use PHP 8.5 como baseline estável. PHP moderno inclui typing opcional forte, attributes, enums, readonly, fibers, pipe operator, extensões e Composer; estilo antigo de PHP 5 não deve definir o caminho.
