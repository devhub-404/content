# Arrays

O tipo de array inclui seu length: `[3]int` e `[4]int` são tipos distintos. Arrays são valores, então assignment e passagem por parâmetro copiam o array salvo uso de ponteiro.

```go
var a [3]int
b := [3]int{10, 20, 30}

fmt.Println(a, b)
```

Arrays são importantes como storage por trás de slices e para valores de tamanho fixo, mas APIs de coleção variável normalmente usam slices. Use array quando o comprimento fixo tem significado.
