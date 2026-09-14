# Strings Terminadas em Nulo

Uma string C comum é uma sequência de bytes `char` diferentes de zero terminada por byte zero. O terminador ocupa storage, mas não faz parte do comprimento lógico. Funções padrão assumem terminação válida e capacidade suficiente conforme seu contrato.

```c
#include <string.h>

char name[32] = "Mina";
size_t length = strlen(name);

if (length + 1 < sizeof name) {
    strcat(name, "!");
}
```

Manipulação de strings é fonte frequente de bugs porque um ponteiro sozinho não carrega capacity. Prefira APIs e abstrações que mantenham tamanho do buffer e length usados explícitos, verifiquem overflow e evitem cópias ou concatenações sem limite.
