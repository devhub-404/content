# Arrays e Limites

Um array C armazena uma quantidade fixa de elementos contíguos do mesmo tipo. O comprimento faz parte do tipo quando o array em si é conhecido. Acessar fora do range válido é undefined behavior.

```c
int values[4] = {10, 20, 30, 40};

for (size_t i = 0; i < 4; ++i) {
    printf("%d
", values[i]);
}
```

Ao passar um array para a maioria das funções, ele converte-se em ponteiro para o primeiro elemento e o comprimento é perdido. Por isso APIs C costumam receber ponteiro mais count explícito. Mantenha os dois valores juntos e valide o count antes de indexar.
