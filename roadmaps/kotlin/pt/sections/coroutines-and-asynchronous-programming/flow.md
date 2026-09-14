# Flow e Streams Assíncronos

`Flow<T>` representa stream assíncrono cold por default: producer roda por collector e pode suspender entre emits. Operators transformam, combinam, bufferizam e controlam execução.

```kotlin
fun updates(): Flow<Int> = flow {
    for (value in 1..3) {
        delay(100)
        emit(value)
    }
}

updates().collect { println(it) }
```

Use Flow para sequência ao longo do tempo, não resultado único. `StateFlow` e `SharedFlow` são hot e têm semânticas diferentes de replay, subscription e lifecycle.
