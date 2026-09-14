# Function Values e Closures

Funções são valores de primeira classe e podem ser armazenadas, passadas e retornadas. Closure captura variáveis do ambiente léxico e elas permanecem vivas enquanto necessárias.

```go
func makeCounter() func() int {
    count := 0

    return func() int {
        count++
        return count
    }
}
```

Closures aparecem em handlers, callbacks, predicates, middleware e goroutines. Seja deliberado com estado mutável capturado, principalmente em concorrência. Capturar objeto grande também pode prolongar seu lifetime.
