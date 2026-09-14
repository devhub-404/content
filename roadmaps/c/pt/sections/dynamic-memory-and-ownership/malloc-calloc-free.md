# `malloc`, `calloc` e `free`

Alocação dinâmica obtém storage cujo lifetime é controlado explicitamente. `malloc` aloca bytes não inicializados, `calloc` aloca e zera conforme contrato e `free` libera uma alocação viva da família apropriada.

```c
size_t count = 100;
int *items = malloc(count * sizeof *items);
if (!items) {
    return -1;
}

/* use items */

free(items);
items = nullptr;
```

Toda alocação bem-sucedida precisa de plano de ownership: quem libera, em quais caminhos e se ownership pode ser transferido. Verifique overflow na aritmética de size, cheque o ponteiro retornado e evite double-free, use-after-free e leaks.
