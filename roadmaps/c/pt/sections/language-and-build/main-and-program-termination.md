# `main` e Término do Programa

Um programa C hosted começa em `main`. As formas portáveis são `int main(void)` e uma forma que recebe argumentos de linha de comando, tradicionalmente `int main(int argc, char *argv[])` ou declaração equivalente. Retornar de `main` termina o programa de forma semelhante a chamar `exit` com aquele status.

```c
#include <stdlib.h>

int main(int argc, char **argv) {
    if (argc < 2) {
        return EXIT_FAILURE;
    }

    return EXIT_SUCCESS;
}
```

Use `EXIT_SUCCESS` e `EXIT_FAILURE` quando a convenção numérica exata deve permanecer portável, ou documente um contrato específico de exit codes para seu ambiente. Não use `void main`; essa não é uma assinatura padrão para programa hosted. Inicialização e término também interagem com `atexit`, streams buffered e recursos específicos do sistema.
