# Files, Streams e Resource Handles

PHP expõe files, sockets, processes e extensions por handles resource/object com close explícito. Streams uniformizam files, memory, wrappers HTTP e protocols.

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

Libere handles escassos rapidamente, especialmente em workers long-lived onde process pode atender milhares de jobs. Mantenha cleanup e tratamento de falhas próximos da operação que adquiriu ou abriu o recurso.
