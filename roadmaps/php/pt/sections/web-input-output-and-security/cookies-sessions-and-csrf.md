# Cookies, Sessions e CSRF

Cookies ficam no client e sessions normalmente associam server-side state a cookie de session ID. Security flags ajudam, mas auth/session também precisa rotation, expiration e logout.

```php
session_start();
$_SESSION['user_id'] = $userId;

setcookie('theme', 'dark', [
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);
```

Requests state-changing precisam CSRF protection quando browser envia credentials automaticamente. SameSite ajuda, mas não substitui estratégia completa.
