# Mutexes, WaitGroups e Once

Package `sync` fornece mutexes, RWMutex, WaitGroups, Once, pools e outras primitives. Use mutex quando várias goroutines compartilham estado mutável e channel não representa naturalmente transferência de ownership.

```go
var mu sync.Mutex
var count int

mu.Lock()
count++
mu.Unlock()
```

WaitGroup coordena completion, mas não propaga erros/cancellation sozinho. `sync.Once` executa inicialização no máximo uma vez. Escolha a primitive mais simples e não copie valores de sync após uso salvo se a documentação permitir.
