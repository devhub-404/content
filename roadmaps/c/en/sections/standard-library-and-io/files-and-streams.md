# Files and Streams

The standard I/O library models files and other byte streams with `FILE *`. Opening selects a mode, reading/writing advances stream state, and `fclose` releases the stream. Text and binary modes can differ on some platforms, so choose the mode that matches the data.

```c
FILE *file = fopen("data.txt", "r");
if (!file) {
    perror("fopen");
    return -1;
}

char line[256];
while (fgets(line, sizeof line, file)) {
    fputs(line, stdout);
}

fclose(file);
```

Check every operation that can fail and distinguish end-of-file from an I/O error when it matters. Buffering means successful writes may not have reached the underlying device yet; `fflush` and close semantics matter at transaction or process boundaries.
