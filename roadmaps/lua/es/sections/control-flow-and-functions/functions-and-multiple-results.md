# Functions y Múltiples Resultados

Las functions son valores de primera clase y pueden retornar varios resultados. Multiple assignment recibe esos resultados por posición, rellenando ausentes con nil y descartando extras. Esto hace ligeros los protocolos result-plus-error e iterators.

```lua
local function divide(a, b)
    if b == 0 then
        return nil, "division by zero"
    end

    return a / b
end

local value, err = divide(10, 2)
print(value, err)
```

La posición de una expresión multi-result importa: en muchas listas solo la última puede expandirse a varios valores. Aprende esta regla en `return`, calls, constructors y varargs, porque los paréntesis o cambiar de posición pueden reducir deliberadamente a un resultado.
