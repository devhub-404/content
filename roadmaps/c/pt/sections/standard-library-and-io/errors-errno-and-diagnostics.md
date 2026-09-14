# `errno`, Erros e Diagnósticos

Algumas funções da biblioteca relatam falha pelo retorno e fornecem informação adicional em `errno`. `errno` só é significativo quando o contrato da função diz que ele foi setado para a falha observada; lê-lo sem checar o resultado principal é erro comum.

```c
#include <errno.h>
#include <stdio.h>

errno = 0;
/* call a function documented to use errno */

if (errno != 0) {
    perror("operation");
}
```

Use `perror` ou `strerror` para diagnóstico humano quando apropriado, mas projete APIs próprias com retornos de erro explícitos e estados documentados. Error codes não são a mesma coisa que exit codes ou signals.
