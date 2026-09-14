# Tiempo, Timers y Tickers

El package `time` modela instants, durations, parsing/formatting, time zones, timers y tickers. `time.Duration` es una duración tipada que evita enteros crudos de milisegundos/segundos.

```go
deadline := time.Now().Add(5 * time.Second)

timer := time.NewTimer(time.Second)
defer timer.Stop()

select {
case <-timer.C:
    fmt.Println(deadline)
case <-ctx.Done():
    return ctx.Err()
}
```

Usa timers/tickers con ownership y stop claros. Calendario/timezone es distinto de medir elapsed time; `time.Time` transporta información de location/monotonic según las operaciones, así que sigue la semántica documentada en comparisons/serialization.
