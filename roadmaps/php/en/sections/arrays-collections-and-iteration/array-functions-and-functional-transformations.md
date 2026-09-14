# Array Functions and Transformations

PHP provides a large family of array functions for mapping, filtering, reducing, sorting, searching, slicing, key/value operations, and set-like transformations. They can make collection logic concise when the callback semantics remain clear.

```php
$activeNames = array_map(
    fn (User $user) => $user->name,
    array_filter($users, fn (User $user) => $user->active),
);
```

Array helpers are eager and usually allocate result arrays. For very large or streaming datasets, generators, iterators, or database-side filtering may avoid unnecessary memory use.
