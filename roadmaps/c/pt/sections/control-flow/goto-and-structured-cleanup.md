# `goto` e Cleanup Estruturado

C inclui `goto`, que transfere controle para um label na mesma função. Raramente é necessário para branching comum, mas em C de baixo nível um caminho forward-only de cleanup pode ser mais claro que muitos níveis aninhados quando vários recursos foram adquiridos.

```c
int save(void) {
    FILE *file = fopen("data.txt", "w");
    if (!file) return -1;

    void *buffer = malloc(4096);
    if (!buffer) goto cleanup_file;

    /* work */
    free(buffer);
    fclose(file);
    return 0;

cleanup_file:
    fclose(file);
    return -1;
}
```

Um label de cleanup deve centralizar liberação de ownership bem definido, não criar fluxo arbitrário. Não salte para dentro de scopes ignorando inicializações necessárias. Funções pequenas e ownership explícito reduzem a necessidade de grafos complexos de cleanup.
