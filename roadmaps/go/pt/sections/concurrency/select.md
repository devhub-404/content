# `select` e Multiplexação

`select` espera múltiplas operações de channel e escolhe uma que pode prosseguir. É central para cancellation, fan-in, timeouts e coordenação. `default` torna o select non-blocking.

```go
select {
case value := <-results:
    use(value)
case <-time.After(time.Second):
    return errors.New("timeout")
}
```

Quando vários cases estão prontos, a escolha não é por prioridade fixa. Evite busy loop com `default` salvo polling intencional. Timers e contexts normalmente são melhores para timeout/cancellation que loops com sleep.
