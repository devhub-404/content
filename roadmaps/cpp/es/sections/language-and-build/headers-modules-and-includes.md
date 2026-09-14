# Headers, Modules e Includes

Los headers siguen siendo la forma dominante de compartir declaraciones, mientras los modules de C++20 ofrecen un mecanismo de lenguaje para interfaces nombradas e imports. Los modules pueden reducir inclusión textual y algunos problemas de macros y nombres, pero el soporte del build system y del compiler sigue importando.

```cpp
// geometry.cppm
export module geometry;

export struct point {
    double x;
    double y;
};

export double length(point p);
```

No trates modules como un simple reemplazo de headers. El proyecto necesita un grafo de build coherente y muchas dependencias seguirán basadas en headers. Para headers, usa include guards fiables o `#pragma once` donde esté soportado y haz que cada header sea autosuficiente.
