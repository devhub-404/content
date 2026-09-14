# Lifecycle de Request e Superglobals

PHP web tradicional expõe request, server, cookies, uploads e forms por superglobals como `$_GET`, `$_POST`, `$_SERVER`, `$_COOKIE` e `$_FILES`. Tudo é input externo não confiável.

```php
<?php
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$query = $_GET['q'] ?? null;

if ($query !== null) {
    echo htmlspecialchars($query, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
}
```

Frameworks normalmente envolvem isso em request objects. Com ou sem framework, parse/valide na boundary e escape output conforme o contexto de destino.
