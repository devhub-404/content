# Generators and `yield`

A function containing `yield` returns a `Generator` that produces values lazily and preserves local execution state between iterations. Generators are useful for large files, pagination, pipelines, and sequence adapters without building full arrays.

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

Because execution is lazy, resources can remain open until the generator finishes or is destroyed. Use `try/finally` or an owning abstraction so early consumer termination still releases handles predictably.
