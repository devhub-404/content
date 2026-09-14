# Funções de Array e Transformações

PHP fornece muitas array functions para map/filter/reduce/sort/search/slice e operações de keys/values. Tornam transforms concisas quando callbacks permanecem claros.

```php
$activeNames = array_map(
    fn (User $user) => $user->name,
    array_filter($users, fn (User $user) => $user->active),
);
```

Helpers são eager e normalmente alocam resultados. Para datasets grandes/streaming, generators, iterators ou filtering no database podem economizar memória.
