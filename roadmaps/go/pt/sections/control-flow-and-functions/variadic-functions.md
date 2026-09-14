# Funções Variádicas

Parâmetro final `...T` permite receber zero ou mais valores e dá à função um slice desses valores. Um slice existente pode ser expandido na chamada com `slice...`.

```go
func sum(values ...int) int {
    total := 0
    for _, value := range values {
        total += value
    }
    return total
}

total := sum(1, 2, 3)
```

Variadic functions servem a listas opcionais homogêneas, não para substituir config estruturada. Quando opções têm significados/tipos diferentes, struct ou functional options comunicam melhor que `...any`.
