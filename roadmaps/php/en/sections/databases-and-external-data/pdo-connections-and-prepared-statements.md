# PDO and Prepared Statements

PDO provides a consistent database-access interface across several drivers. Prepared statements separate SQL structure from parameter values, reducing injection risk and making type/value binding explicit.

```php
$pdo = new PDO($dsn, $user, $password, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT id, name FROM users WHERE email = :email');
$stmt->execute(['email' => $email]);
```

Prepared parameters cannot replace every dynamic SQL fragment such as arbitrary table names or sort directions; those structural choices need allowlists or query builders. Transactions, isolation, timeouts, and connection lifecycle remain part of correct database design.
