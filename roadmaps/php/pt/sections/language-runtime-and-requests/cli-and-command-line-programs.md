# Programas CLI

PHP possui SAPI de linha de comando com `$argv`/`$argc` e acesso normal a files, processes, sockets, databases e packages. CLI não segue as mesmas assumptions de request HTTP.

```php
<?php
$args = $argv;
$script = array_shift($args);

foreach ($args as $arg) {
    echo $arg, PHP_EOL;
}
```

Mantenha entry scripts CLI finos: parse arguments e chame services comuns. Assim core code é compartilhado entre web, jobs, tests e commands.
