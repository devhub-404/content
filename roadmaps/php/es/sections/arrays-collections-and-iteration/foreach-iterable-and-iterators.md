# `foreach`, `iterable` e Iterators

`foreach` itera arrays y objects `Traversable`, y el type `iterable` acepta ambos. SPL ofrece interfaces/implementations de iterator.

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

Prefiere `foreach` para recorrido normal. Los custom iterators sirven cuando lazy traversal forma parte real de la abstracción. Elige la forma de iteración según el contrato de los datos y evita ocultar recorridos complejos tras abstracciones innecesarias.
