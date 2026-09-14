# Transactions

Transaction agrupa mudanças com commit/rollback conforme database/isolation. Código precisa garantir rollback em falhas e manter scope curto.

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

Não faça network call lenta ou espere usuário dentro da transaction. Retry apenas erros seguros e considere idempotency com side effects externos. Trate a fronteira externa como não confiável e mantenha conversão, validação e error handling explícitos.
