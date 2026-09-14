# Headers, Modules e Includes

Headers continuam sendo a forma dominante de compartilhar declarações, enquanto modules do C++20 oferecem mecanismo de linguagem para interfaces nomeadas e imports. Modules podem reduzir inclusão textual e alguns problemas de macro/name leakage, mas suporte de build system e compiler ainda influencia a adoção.

```cpp
// geometry.cppm
export module geometry;

export struct point {
    double x;
    double y;
};

export double length(point p);
```

Não trate modules como search-and-replace de headers. O projeto precisa de um grafo de build coerente e dependências podem continuar header-based. Para headers, use include guards confiáveis ou `#pragma once` quando suportado e faça cada header ser autocontido.
