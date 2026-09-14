# Type Sets e Constraints de Underlying Type

Interfaces de constraint podem descrever type sets com unions e aproximações como `~int`, incluindo tipos definidos cujo underlying type é `int`. Isso aceita domain types preservando o tipo exato no resultado.

```go
type Integer interface {
    ~int | ~int32 | ~int64
}

func Double[T Integer](value T) T {
    return value * 2
}
```

Type-set syntax é para constraints, não interfaces runtime comuns em qualquer contexto. Mantenha constraints pequenos e semânticos. Uma union enorme de tipos concretos normalmente indica abstração ruim.
