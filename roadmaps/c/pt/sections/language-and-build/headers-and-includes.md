# Headers e `#include`

Headers normalmente contêm declarações, definições de tipos, macros e definições inline compartilhadas entre translation units. `#include` é preprocessamento textual: os tokens do arquivo incluído passam a fazer parte da translation unit antes da compilação C propriamente dita.

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

Use include guards ou outro mecanismo suportado para que o header possa ser incluído repetidamente sem definições duplicadas. Um header deve incluir as dependências necessárias para suas próprias declarações em vez de depender de uma ordem acidental de includes no source consumidor.
