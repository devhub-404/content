# Programas CLI

PHP tiene una SAPI de línea de comandos con `$argv`/`$argc` y acceso normal a files, processes, sockets, databases y packages. CLI no sigue las mismas assumptions de request HTTP.

```php
<?php
$args = $argv;
$script = array_shift($args);

foreach ($args as $arg) {
    echo $arg, PHP_EOL;
}
```

Mantén entry scripts CLI delgados: parsea argumentos y llama services comunes. Así core code se comparte entre web, jobs, tests y commands.
