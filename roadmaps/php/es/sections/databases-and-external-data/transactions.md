# Transactions

Una transaction agrupa cambios con commit/rollback según database/isolation. El código debe garantizar rollback en fallos y mantener el scope corto.

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

No hagas network calls lentas ni esperes al usuario dentro de la transaction. Reintenta solo errores seguros y considera idempotency con side effects externos.
