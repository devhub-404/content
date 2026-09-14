# Lambdas y Captures

Una lambda crea un closure object sin nombre con `operator()` y una lista explícita de captures. Puede copiar valores, mantener referencias, inicializar nuevos miembros o capturar `this` según la sintaxis.

```cpp
int factor = 3;

auto multiply = [factor](int value) {
    return value * factor;
};

std::ranges::transform(values, out.begin(), multiply);
```

El closure puede vivir más que el scope original, así que las captures por referencia no deben sobrevivir a los objetos referenciados. Prefiere captures pequeñas frente a `[&]` o `[=]` en callbacks long-lived. Las generic lambdas pueden usar parámetros `auto` o template parameters explícitos.
