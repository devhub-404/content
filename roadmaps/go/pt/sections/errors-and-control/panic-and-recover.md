# `panic` e `recover`

`panic` inicia stack unwinding da goroutine atual e executa deferred functions. `recover` intercepta panic apenas quando usado adequadamente em função deferred da mesma goroutine.

```go
func mustPositive(value int) {
    if value <= 0 {
        panic("value must be positive")
    }
}
```

Panic serve a invariantes de programação realmente impossíveis ou algumas falhas de inicialização, não erros normais de input/rede/arquivo que callers podem tratar. Libraries devem evitar panic em condições rotineiras.
