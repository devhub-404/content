# Design de API e Interfaces Pequenas

APIs idiomáticas tendem a aceitar comportamento por interfaces pequenas e retornar tipos concretos. Isso permite ao producer expor methods úteis enquanto consumers dependem apenas da capacidade necessária.

```go
type Clock interface {
    Now() time.Time
}

func NewService(clock Clock) *Service {
    return &Service{clock: clock}
}
```

Evite criar interface ao lado de toda implementação por antecipação. Muitas vezes o consumer deve defini-la quando precisa substituição. Prefira zero value útil, errors claros, context explícito e structs simples.
