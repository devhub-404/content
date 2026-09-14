# Ponteiros de Função e Callbacks

Funções podem ser referenciadas por ponteiros de função e passadas como callbacks. É assim que APIs como `qsort` recebem comportamento do caller e como bibliotecas C modelam handlers, políticas e interfaces de plugin.

```c
typedef int (*compare_fn)(const void *, const void *);

int compare_ints(const void *a, const void *b) {
    const int left = *(const int *)a;
    const int right = *(const int *)b;
    return (left > right) - (left < right);
}
```

O tipo do ponteiro precisa corresponder à assinatura real. Callbacks genéricos com `void *` deslocam parte da verificação de tipos para casts dentro do callback, então documente bem o contrato. Typedefs específicos do domínio tornam essas APIs mais legíveis.
