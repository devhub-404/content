# Flow y Streams Asíncronos

`Flow<T>` representa un stream asíncrono cold por defecto: el producer corre por collector y puede suspender entre emits. Los operators transforman, combinan, bufferizan y controlan ejecución.

```kotlin
fun updates(): Flow<Int> = flow {
    for (value in 1..3) {
        delay(100)
        emit(value)
    }
}

updates().collect { println(it) }
```

Usa Flow para una secuencia a lo largo del tiempo, no para un único resultado. `StateFlow` y `SharedFlow` son hot y tienen semánticas distintas de replay, subscription y lifecycle.
