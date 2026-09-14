# Archivos y Streams

La biblioteca estándar modela archivos y otros byte streams con `FILE *`. Abrir selecciona un modo, reads/writes avanzan el estado y `fclose` libera el stream. Los modos text y binary pueden diferir entre plataformas, así que elige según los datos.

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

Comprueba las operaciones que pueden fallar y distingue EOF de error cuando sea necesario. El buffering significa que un write exitoso quizá aún no haya llegado al dispositivo; `fflush` y el cierre importan en fronteras de transacción o proceso.
