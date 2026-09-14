# `foreach`, `iterable`, and Iterators

`foreach` iterates arrays and `Traversable` objects, while the `iterable` type accepts either category. SPL provides iterator interfaces and reusable iterator implementations for custom traversal behavior.

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

Prefer `foreach` for ordinary traversal. Custom iterators are useful when lazy traversal is part of a reusable abstraction; do not implement iterator protocols solely to make a one-off loop look clever.
