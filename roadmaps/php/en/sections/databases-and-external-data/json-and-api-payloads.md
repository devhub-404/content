# JSON and API Payloads

JSON functions convert between JSON text and PHP arrays/objects/scalars. `JSON_THROW_ON_ERROR` makes malformed or unencodable data fail through exceptions rather than requiring a separate global error check.

```php
$data = json_decode($json, true, flags: JSON_THROW_ON_ERROR);

$response = json_encode(
    ['id' => 42, 'name' => 'Mina'],
    JSON_THROW_ON_ERROR,
);
```

Decoded JSON is still untrusted and dynamically shaped. Validate required keys, types, ranges, and domain rules before constructing core objects. Define a stable serialization contract instead of exposing arbitrary object internals.
