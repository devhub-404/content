# Undefined Behavior e Abstract Machine

C++ define uma abstract machine e permite otimizações desde que o comportamento observável de programas válidos seja preservado. Undefined behavior quebra esse contrato: após a operação inválida, a implementação não tem obrigações. Overflow signed, use-after-lifetime, dereference inválido, data race e out-of-bounds são exemplos comuns.

```cpp
#include <limits>

int safe_increment(int x) {
    if (x == std::numeric_limits<int>::max()) {
        return x;
    }
    return x + 1;
}
```

Otimização pode tornar UB surpreendente porque o compilador assume que ele não ocorre. Trate warnings, sanitizers, regras de lifetime e preconditions da standard library como parte normal da correção, não extras opcionais de debugging.
