# Fibers and Cooperative Concurrency

Fibers provide low-level cooperative execution that can suspend and resume call stacks. Async frameworks and event-loop libraries can use fibers to offer synchronous-looking APIs over nonblocking operations.

```php
$fiber = new Fiber(function (): void {
    $value = Fiber::suspend('paused');
    echo $value;
});

$state = $fiber->start();
$fiber->resume('resumed');
```

Application code rarely needs to manage fibers directly. Use a mature async framework or event-loop library when concurrency is required, because scheduling, cancellation, I/O readiness, and resource cleanup form a larger system than the Fiber API alone.
