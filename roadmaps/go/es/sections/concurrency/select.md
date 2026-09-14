# `select` y Multiplexación

`select` espera varias operaciones de channel y elige una que pueda avanzar. Es central para cancellation, fan-in, timeouts y coordinación. `default` vuelve el select non-blocking.

```go
select {
case value := <-results:
    use(value)
case <-time.After(time.Second):
    return errors.New("timeout")
}
```

Cuando varios cases están listos, la elección no sigue una prioridad fija. Evita busy loops con `default` salvo polling intencional. Timers y contexts suelen ser mejores para timeout/cancellation que loops con sleep.
