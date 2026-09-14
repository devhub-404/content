# Generators e `yield`

Function com `yield` retorna `Generator` lazy e preserva estado local. É útil para files grandes, pagination e pipelines sem arrays completos.

```php
function lines(string $path): Generator {
    $file = fopen($path, 'rb');
    try {
        while (($line = fgets($file)) !== false) {
            yield rtrim($line, "
");
        }
    } finally {
        fclose($file);
    }
}
```

Como execução é lazy, recursos podem ficar abertos até terminar. Use `try/finally` ou ownership claro para early termination. Escolha a forma de iteração pelo contrato dos dados e evite esconder traversal complexo atrás de uma abstração desnecessária.
