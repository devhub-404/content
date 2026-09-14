# `goto` and Structured Cleanup

C includes `goto`, which transfers control to a label in the same function. It is rarely needed for ordinary branching, but in low-level C a forward-only cleanup path can be clearer than deeply nested error handling when several resources have been acquired.

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

A cleanup label should centralize well-defined ownership release, not create arbitrary control flow. Do not jump into a scope in ways that bypass required initialization or make object lifetime hard to reason about. Small functions and explicit ownership reduce the need for complex cleanup graphs.
