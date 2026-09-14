# Funciones de Array y Transformaciones

PHP ofrece muchas array functions para map/filter/reduce/sort/search/slice y operaciones de keys/values. Hacen transforms concisas cuando los callbacks siguen claros.

```php
$activeNames = array_map(
    fn (User $user) => $user->name,
    array_filter($users, fn (User $user) => $user->active),
);
```

Los helpers son eager y normalmente asignan resultados. Para datasets grandes/streaming, generators, iterators o filtrado en database pueden ahorrar memoria.
