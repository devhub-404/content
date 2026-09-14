# Diseño de API e Interfaces Pequeñas

Las APIs idiomáticas tienden a aceptar comportamiento mediante interfaces pequeñas y retornar tipos concretos. Esto permite al producer exponer methods útiles mientras los consumers dependen solo de la capacidad necesaria.

```go
type Clock interface {
    Now() time.Time
}

func NewService(clock Clock) *Service {
    return &Service{clock: clock}
}
```

Evita crear interfaces preventivamente junto a cada implementación. A menudo el consumer debe definirla cuando necesite sustitución. Prefiere zero values útiles, errores claros, context explícito y structs simples.
