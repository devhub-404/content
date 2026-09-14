# Transactions

A transaction groups database changes into a unit with commit or rollback semantics according to the database engine and isolation level. Application code must ensure rollback on every failure path and keep the transaction scope as short as practical.

```php
$pdo->beginTransaction();
try {
    debit($pdo, $from, $amount);
    credit($pdo, $to, $amount);
    $pdo->commit();
} catch (Throwable $e) {
    $pdo->rollBack();
    throw $e;
}
```

Do not perform slow network calls or wait for user interaction while holding a database transaction. Design retries only for errors that are safe to retry and understand how idempotency interacts with external side effects.
