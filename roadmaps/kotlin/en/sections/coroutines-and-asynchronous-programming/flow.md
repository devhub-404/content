# Flow and Asynchronous Streams

`Flow<T>` represents a cold asynchronous stream by default: the producer runs for each collector and can suspend between emitted values. Operators transform, combine, buffer, debounce, retry, and control execution of flows.

```kotlin
fun updates(): Flow<Int> = flow {
    for (value in 1..3) {
        delay(100)
        emit(value)
    }
}

updates().collect { println(it) }
```

Use Flow for sequences over time rather than a single asynchronous result. Understand hot flows such as `StateFlow` and `SharedFlow` separately because they have ownership, replay, subscription, and lifecycle semantics that differ from a cold flow.
