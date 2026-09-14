# Variáveis e Zero Values

Toda variável Go possui zero value definido quando declarada sem initializer. Números viram zero, bools false, strings vazias e pointers/interfaces/slices/maps/channels/functions possuem estados nil apropriados.

```go
var count int
var ready bool
var name string

fmt.Println(count, ready, name)
// 0 false ""
```

Projete tipos para que o zero value seja útil quando possível. Muitos tipos padrão, como `sync.Mutex` e `bytes.Buffer`, podem ser usados imediatamente. Zero value útil reduz constructors desnecessários e simplifica inicialização.
