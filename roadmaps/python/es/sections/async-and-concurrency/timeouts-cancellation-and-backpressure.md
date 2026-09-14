# Timeouts, Cancellation y Backpressure

La cancellation async es cooperativa y suele llegar como `CancelledError` en suspension points. Los timeouts crean scopes y bounded queues/semaphores ofrecen backpressure.

```python
async with asyncio.timeout(5):
    result = await service.load()

queue = asyncio.Queue(maxsize=100)
```

No tragues la cancellation en broad exception handling. Limita concurrencia sobre recursos escasos y define el owner de retries/timeouts.
