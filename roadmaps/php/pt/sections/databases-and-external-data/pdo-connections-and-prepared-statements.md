# PDO e Prepared Statements

PDO fornece interface consistente para vários drivers. Prepared statements separam SQL structure de values e reduzem injection risk.

```php
$pdo = new PDO($dsn, $user, $password, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT id, name FROM users WHERE email = :email');
$stmt->execute(['email' => $email]);
```

Parameters não substituem dynamic SQL estrutural como table names/order; use allowlists/query builders. Transactions, isolation, timeout e lifecycle continuam importantes. Trate a fronteira externa como não confiável e mantenha conversão, validação e error handling explícitos.
