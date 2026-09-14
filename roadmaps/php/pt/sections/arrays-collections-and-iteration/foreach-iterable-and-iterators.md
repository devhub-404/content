# `foreach`, `iterable` e Iterators

`foreach` itera arrays e objects `Traversable`, e type `iterable` aceita ambos. SPL fornece interfaces/implementations de iterator.

```php
foreach ($users as $id => $user) {
    echo $id, ': ', $user->name, PHP_EOL;
}

function names(iterable $users): iterable {
    foreach ($users as $user) {
        yield $user->name;
    }
}
```

Prefira `foreach` no traversal comum. Custom iterators servem quando lazy traversal é parte real da abstração. Escolha a forma de iteração pelo contrato dos dados e evite esconder traversal complexo atrás de uma abstração desnecessária.
