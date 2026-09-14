# Lifecycle de Request y Superglobals

PHP web tradicional expone request, server, cookies, uploads y forms mediante superglobals como `$_GET`, `$_POST`, `$_SERVER`, `$_COOKIE` y `$_FILES`. Todo es input externo no confiable.

```php
<?php
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$query = $_GET['q'] ?? null;

if ($query !== null) {
    echo htmlspecialchars($query, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
}
```

Los frameworks suelen envolverlo en request objects. Con o sin framework, parsea/valida en el boundary y escapa output según el contexto de destino.
