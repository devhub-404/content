# Aritmética de Ponteiros e Percurso de Arrays

Aritmética de ponteiros é definida em relação a um objeto array. Somar inteiro avança por elementos, não bytes brutos, e é permitido formar ponteiro one-past para comparação ou subtração, mas não dereference nessa posição.

```c
int values[] = {10, 20, 30};

for (int *p = values; p != values + 3; ++p) {
    printf("%d
", *p);
}
```

Subtração e ordenação só fazem sentido dentro das relações permitidas pelo padrão. Para percorrer representação byte a byte use ponteiros a character types. Prefira indexação quando ela comunica melhor a intenção.
