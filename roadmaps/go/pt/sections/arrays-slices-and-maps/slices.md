# Slices, Length, Capacity e `append`

Slice é descriptor sobre array subjacente com length e capacity. Slicing cria outra view e `append` aumenta a sequência, podendo alocar novo backing array quando a capacity não basta.

```go
values := make([]int, 0, 4)
values = append(values, 10, 20, 30)

fmt.Println(len(values), cap(values))
```

Vários slices podem compartilhar o mesmo backing array, então mutation por um pode afetar outro. Sempre use o slice retornado por `append`. Pré-aloque capacity quando há boa estimativa, sem exagero.
