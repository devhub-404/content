# PDO y Prepared Statements

PDO ofrece una interfaz consistente para varios drivers. Los prepared statements separan SQL structure de values y reducen injection risk.

```php
$pdo = new PDO($dsn, $user, $password, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT id, name FROM users WHERE email = :email');
$stmt->execute(['email' => $email]);
```

Los parameters no sustituyen dynamic SQL estructural como table names/order; usa allowlists/query builders. Transactions, isolation, timeout y lifecycle siguen siendo importantes.
