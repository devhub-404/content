# Headers y `#include`

Los headers suelen contener declaraciones, definiciones de tipos, macros y definiciones inline que varias translation units necesitan compartir. `#include` es preprocesamiento textual: los tokens incluidos pasan a formar parte de la translation unit antes de la compilación C propiamente dicha.

```c
// point.h
#ifndef POINT_H
#define POINT_H

struct point {
    double x;
    double y;
};

double distance_from_origin(struct point p);

#endif
```

Usa include guards u otro mecanismo compatible para que un header pueda incluirse varias veces sin duplicar definiciones. Un header debe incluir las dependencias que necesita para sus propias declaraciones y no depender de un orden accidental de includes en el archivo consumidor.
