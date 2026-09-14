# `errno`, Errores y Diagnósticos

Algunas funciones de la biblioteca informan fallo mediante su retorno y aportan información adicional en `errno`. `errno` solo es significativo cuando el contrato de la función dice que se establece para el fallo observado; leerlo sin comprobar el resultado principal es un error común.

```c
#include <errno.h>
#include <stdio.h>

errno = 0;
/* call a function documented to use errno */

if (errno != 0) {
    perror("operation");
}
```

Usa `perror` o `strerror` para diagnósticos humanos cuando corresponda, pero diseña tus propias APIs con retornos de error explícitos y estados documentados. Los error codes no son lo mismo que exit codes o signals.
