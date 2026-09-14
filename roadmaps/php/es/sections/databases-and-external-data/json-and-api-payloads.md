# JSON y Payloads de API

Las JSON functions convierten texto JSON en arrays/objects/scalars y viceversa. `JSON_THROW_ON_ERROR` convierte failures en exceptions.

```php
$data = json_decode($json, true, flags: JSON_THROW_ON_ERROR);

$response = json_encode(
    ['id' => 42, 'name' => 'Mina'],
    JSON_THROW_ON_ERROR,
);
```

El JSON decoded sigue siendo untrusted y dynamic. Valida keys/types/ranges y construye domain objects. Define un contract de serialización estable. Trata la frontera externa como no confiable y mantén conversión, validación y error handling explícitos.
