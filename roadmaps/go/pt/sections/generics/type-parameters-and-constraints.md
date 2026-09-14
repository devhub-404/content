# Type Parameters e Constraints

Funções e tipos genéricos declaram type parameters com constraints. Constraint é interface usada em contexto de type parameter para descrever type set e operações permitidas.

```go
func Max[T cmp.Ordered](a, b T) T {
    if a > b {
        return a
    }
    return b
}
```

Use generics quando algoritmo/estrutura realmente preserva relação entre vários tipos. Não substitua interfaces comportamentais automaticamente. Interfaces fornecem polimorfismo runtime; generics, parametrização de compile time.
