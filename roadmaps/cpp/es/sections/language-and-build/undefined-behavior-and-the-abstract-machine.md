# Undefined Behavior y Abstract Machine

C++ define una abstract machine y permite optimizaciones siempre que se preserve el comportamiento observable de programas bien definidos. Undefined behavior rompe ese contrato: tras la operación inválida, la implementación no tiene obligaciones. Overflow signed, use-after-lifetime, dereference inválido, data races y out-of-bounds son ejemplos comunes.

```cpp
#include <limits>

int safe_increment(int x) {
    if (x == std::numeric_limits<int>::max()) {
        return x;
    }
    return x + 1;
}
```

La optimización puede hacer que el UB aparezca de formas sorprendentes porque el compilador puede asumir que nunca ocurre. Trata warnings, sanitizers, reglas de lifetime y preconditions de la standard library como parte normal de la corrección.
