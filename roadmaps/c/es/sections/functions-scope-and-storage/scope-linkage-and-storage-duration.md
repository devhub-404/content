# Scope, Linkage y Storage Duration

Scope responde dónde es visible un nombre, linkage si declaraciones en lugares distintos se refieren a la misma entidad y storage duration cuánto tiempo existe un objeto. Son conceptos separados aunque keywords como `static` participen en varios.

```c
static int file_counter;

void tick(void) {
    static int calls;
    ++calls;
    ++file_counter;
}
```

Un local de bloque suele tener automatic storage. Un nombre `static` en file scope tiene internal linkage, mientras un objeto `static` en block scope vive durante todo el programa. Aprende cada efecto en vez de traducir `static` a una idea vaga como «global».
