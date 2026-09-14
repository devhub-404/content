# Fibers y Concurrencia Cooperativa

Los Fibers ofrecen ejecución cooperativa low-level con suspend/resume de call stack. Los frameworks async pueden usarlos para APIs sync-looking sobre I/O nonblocking.

```php
$fiber = new Fiber(function (): void {
    $value = Fiber::suspend('paused');
    echo $value;
});

$state = $fiber->start();
$fiber->resume('resumed');
```

El application code rara vez debería gestionar Fiber directamente. Usa un framework/event loop maduro porque scheduling, cancellation y cleanup van más allá de la API Fiber.
