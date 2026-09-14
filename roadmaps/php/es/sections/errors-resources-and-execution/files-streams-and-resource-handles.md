# Files, Streams y Resource Handles

PHP expone files, sockets, processes y extensions mediante handles resource/object con cierre explícito. Streams uniformizan files, memory, wrappers HTTP y protocols.

```php
$handle = fopen($path, 'rb');
if ($handle === false) {
    throw new RuntimeException('cannot open file');
}

try {
    $data = stream_get_contents($handle);
} finally {
    fclose($handle);
}
```

Libera handles escasos pronto, especialmente en workers long-lived donde el proceso puede atender miles de jobs. Mantén cleanup y tratamiento de fallos cerca de la operación que adquirió o abrió el recurso.
