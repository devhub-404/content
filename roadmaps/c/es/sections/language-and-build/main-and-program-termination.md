# `main` y Terminación del Programa

Un programa C hosted empieza en `main`. Las formas portables son `int main(void)` y una forma que recibe argumentos de línea de comandos, tradicionalmente `int main(int argc, char *argv[])` o una declaración equivalente. Retornar desde `main` termina el programa de forma similar a llamar `exit` con ese estado.

```c
#include <stdlib.h>

int main(int argc, char **argv) {
    if (argc < 2) {
        return EXIT_FAILURE;
    }

    return EXIT_SUCCESS;
}
```

Usa `EXIT_SUCCESS` y `EXIT_FAILURE` cuando quieras mantener portable la convención numérica, o documenta un contrato propio de códigos de salida. No uses `void main`; no es una firma estándar de un programa hosted. Inicio y terminación también interactúan con handlers de `atexit`, streams buffered y funciones específicas del sistema.
