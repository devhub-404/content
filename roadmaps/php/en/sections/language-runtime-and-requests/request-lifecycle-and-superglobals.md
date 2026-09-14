# Request Lifecycle and Superglobals

Traditional web PHP exposes request, server, cookie, session, file-upload, environment, and form data through superglobals such as `$_GET`, `$_POST`, `$_SERVER`, `$_COOKIE`, and `$_FILES`. These values are external input and must be treated as untrusted.

```php
<?php
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$query = $_GET['q'] ?? null;

if ($query !== null) {
    echo htmlspecialchars($query, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
}
```

Frameworks usually wrap superglobals in request objects, which improves testability and normalization. Whether using a framework or not, parse and validate input at the boundary and escape output for the destination context instead of trusting raw request strings.
