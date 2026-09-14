# Cookies, Sessions, and CSRF

Cookies are client-stored data sent with matching requests, while PHP sessions commonly associate a server-side state record with a session identifier cookie. Cookie security flags reduce exposure, but authentication/session design also needs fixation, rotation, expiration, and logout policies.

```php
session_start();
$_SESSION['user_id'] = $userId;

setcookie('theme', 'dark', [
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);
```

State-changing requests need CSRF protection when browser credentials are sent automatically. SameSite cookies help but do not replace a complete strategy for every cross-origin flow and browser compatibility requirement.
