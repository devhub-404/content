# Timeouts, Cancellation e Backpressure

Cancellation async é cooperativa e normalmente chega como `CancelledError` em suspension points. Timeouts criam scopes e bounded queues/semaphores fornecem backpressure.

```python
async with asyncio.timeout(5):
    result = await service.load()

queue = asyncio.Queue(maxsize=100)
```

Não engula cancellation em broad exception handling. Limite concorrência em recursos escassos e defina owner de retries/timeouts. Estruture o lifetime das tasks para que falhas, cancelamento e cleanup tenham um owner claro.
