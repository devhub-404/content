# Tempo, Timers e Tickers

Package `time` modela instants, durations, parsing/formatting, time zones, timers e tickers. `time.Duration` é duration tipada, evitando inteiros crus de milissegundos/segundos.

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

Use timers/tickers com ownership e stop claros. Calendário/timezone difere de medir elapsed time; `time.Time` carrega informações de location/monotonic conforme operações, então siga semântica documentada em comparisons/serialization.
