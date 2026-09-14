# Lambdas e Captures

Uma lambda cria um closure object sem nome com `operator()` e uma capture list explícita. Captures podem copiar valores, manter referências, inicializar novos membros ou capturar `this` conforme a sintaxe.

```cpp
int factor = 3;

auto multiply = [factor](int value) {
    return value * factor;
};

std::ranges::transform(values, out.begin(), multiply);
```

O closure pode viver além do scope original, então captures por referência não podem sobreviver aos objetos referenciados. Prefira captures pequenas a `[&]` ou `[=]` em callbacks long-lived. Generic lambdas podem usar parâmetros `auto` ou template parameters explícitos.
