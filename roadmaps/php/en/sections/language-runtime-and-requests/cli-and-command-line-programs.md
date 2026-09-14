# CLI Programs

PHP includes a command-line SAPI that exposes arguments through `$argv`/`$argc` and provides normal access to files, processes, sockets, databases, and Composer packages. CLI programs do not have the same request superglobal assumptions as HTTP execution.

```php
<?php
$args = $argv;
$script = array_shift($args);

foreach ($args as $arg) {
    echo $arg, PHP_EOL;
}
```

Use CLI entry scripts as thin boundaries that parse arguments and call ordinary application services. This keeps core code shared between web, jobs, tests, and commands instead of embedding all logic in one script.
