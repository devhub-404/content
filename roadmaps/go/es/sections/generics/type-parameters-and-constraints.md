# Type Parameters y Constraints

Las funciones y tipos genéricos declaran type parameters con constraints. Un constraint es una interface usada en contexto de type parameter para describir el type set y las operaciones permitidas.

```go
func Max[T cmp.Ordered](a, b T) T {
    if a > b {
        return a
    }
    return b
}
```

Usa generics cuando un algoritmo o estructura realmente preserve una relación entre varios tipos. No sustituyas interfaces de comportamiento automáticamente. Las interfaces ofrecen polimorfismo runtime; los generics, parametrización de compile time.
