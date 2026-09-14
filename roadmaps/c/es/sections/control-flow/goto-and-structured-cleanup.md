# `goto` y Cleanup Estructurado

C incluye `goto`, que transfiere control a un label dentro de la misma función. Rara vez hace falta para branching normal, pero en C de bajo nivel una ruta de cleanup solo hacia delante puede ser más clara que muchos niveles anidados cuando se han adquirido varios recursos.

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

Un label de cleanup debe centralizar la liberación de ownership bien definido, no crear flujo arbitrario. No saltes a scopes saltándote inicializaciones necesarias. Funciones pequeñas y ownership explícito reducen la necesidad de grafos complejos de cleanup.
