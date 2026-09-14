# Type Sets y Constraints de Underlying Type

Las interfaces de constraint pueden describir type sets con unions y aproximaciones como `~int`, incluyendo tipos definidos cuyo underlying type es `int`. Así se aceptan domain types conservando el tipo exacto en el resultado.

```go
type Integer interface {
    ~int | ~int32 | ~int64
}

func Double[T Integer](value T) T {
    return value * 2
}
```

La type-set syntax es para constraints, no para interfaces runtime ordinarias en cualquier contexto. Mantén constraints pequeños y semánticos. Una union enorme de tipos concretos suele indicar una abstracción pobre.
