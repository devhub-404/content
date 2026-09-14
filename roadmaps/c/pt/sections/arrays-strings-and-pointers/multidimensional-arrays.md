# Arrays Multidimensionais

Um array multidimensional em C é um array cujos elementos também são arrays. O storage de arrays aninhados comuns é contíguo em row-major order. As dimensões internas fazem parte do tipo e são necessárias para calcular o passo entre linhas.

```c
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6},
};

printf("%d
", matrix[1][2]);
```

Parâmetros de função para arrays multidimensionais precisam descrever dimensões suficientes para o compilador calcular endereços, ou usar buffer flat com dimensões/strides explícitos. Escolha uma representação e documente o layout.
