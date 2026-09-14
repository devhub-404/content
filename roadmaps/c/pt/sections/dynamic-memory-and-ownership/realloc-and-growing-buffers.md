# `realloc` e Buffers Crescentes

`realloc` altera o tamanho de uma alocação e pode manter o endereço ou mover os dados. Em falha, a alocação original continua válida, por isso atribuir diretamente o retorno ao único ponteiro pode perder o bloco antigo.

```c
size_t new_count = count * 2;
int *tmp = realloc(items, new_count * sizeof *items);

if (tmp) {
    items = tmp;
    count = new_count;
}
```

Use ponteiro temporário e atualize ownership apenas após sucesso. Calcule o novo size com verificação de overflow. Em C23, `realloc(ptr, 0)` é undefined behavior, então trate tamanho zero explicitamente.
