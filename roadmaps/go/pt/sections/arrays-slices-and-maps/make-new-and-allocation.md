# `make`, `new` e Alocação

`new(T)` aloca storage zerado para um `T` e retorna `*T`. `make` inicializa a representação runtime de slices, maps e channels e retorna o próprio valor, não ponteiro.

```go
values := make([]int, 10)
lookup := make(map[string]int)

ptr := new(int)
*ptr = 42
```

Muito código Go usa literals e zero values em vez dessas funções. O compilador decide stack ou heap por escape analysis; `new` no source não significa diretamente “heap allocation” no sentido de C.
