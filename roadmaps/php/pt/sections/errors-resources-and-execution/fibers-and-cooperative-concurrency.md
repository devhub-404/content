# Fibers e Concorrência Cooperativa

Fibers fornecem execução cooperativa low-level com suspend/resume de call stack. Async frameworks podem usar fibers para APIs sync-looking sobre I/O nonblocking.

```php
$fiber = new Fiber(function (): void {
    $value = Fiber::suspend('paused');
    echo $value;
});

$state = $fiber->start();
$fiber->resume('resumed');
```

Application code raramente gerencia Fiber direto. Use framework/event loop maduro porque scheduling, cancellation e cleanup vão além da API Fiber.
