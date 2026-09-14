# Qué es PHP

PHP es un lenguaje dinámicamente tipado de propósito general con fuerte uso web, pero también ejecuta CLI, workers, daemons y tooling. En despliegue común, el código corre por request mediante PHP-FPM u otra integración de server, aunque runtimes modernos también mantienen workers vivos.

```php
<?php
$name = 'Mina';
echo "Hello, {$name}!
";
```

Usa PHP 8.5 como baseline estable. PHP moderno incluye typing opcional fuerte, attributes, enums, readonly, fibers, pipe operator, extensiones y Composer; el estilo antiguo de PHP 5 no debe definir el camino.
