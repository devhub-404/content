# Strings Terminadas en Nulo

Una string C ordinaria es una secuencia de bytes `char` no nulos terminada por un byte cero. El terminador ocupa almacenamiento pero no cuenta en la longitud lógica. Las funciones estándar asumen terminación válida y capacidad suficiente según su contrato.

```c
#include <string.h>

char name[32] = "Mina";
size_t length = strlen(name);

if (length + 1 < sizeof name) {
    strcat(name, "!");
}
```

El manejo de strings es una fuente importante de bugs porque un puntero solo no incluye capacity. Prefiere APIs y abstracciones que mantengan explícitos el tamaño del buffer y la longitud usada, comprueben overflow y eviten copias o concatenaciones sin límite.
