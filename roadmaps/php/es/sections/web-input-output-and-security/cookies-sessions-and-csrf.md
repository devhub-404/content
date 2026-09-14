# Cookies, Sessions y CSRF

Las cookies viven en el client y sessions suelen asociar server-side state a una cookie de session ID. Los security flags ayudan, pero auth/session también necesita rotation, expiration y logout.

```php
session_start();
$_SESSION['user_id'] = $userId;

setcookie('theme', 'dark', [
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);
```

Los requests state-changing necesitan CSRF protection cuando el browser envía credentials automáticamente. SameSite ayuda, pero no sustituye una estrategia completa.
