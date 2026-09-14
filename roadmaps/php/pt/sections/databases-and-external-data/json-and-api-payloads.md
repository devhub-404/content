# JSON e Payloads de API

JSON functions convertem texto JSON em arrays/objects/scalars e vice-versa. `JSON_THROW_ON_ERROR` transforma failures em exceptions.

```php
$data = json_decode($json, true, flags: JSON_THROW_ON_ERROR);

$response = json_encode(
    ['id' => 42, 'name' => 'Mina'],
    JSON_THROW_ON_ERROR,
);
```

JSON decoded continua untrusted e dynamic. Valide keys/types/ranges e construa domain objects. Defina contract de serialization estável. Trate a fronteira externa como não confiável e mantenha conversão, validação e error handling explícitos.
