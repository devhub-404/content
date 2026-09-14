# Functions e Múltiplos Resultados

Functions são valores de primeira classe e podem retornar vários resultados. Multiple assignment recebe resultados por posição, preenchendo ausentes com nil e descartando extras. Isso torna protocolos result-plus-error e iterators leves.

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

A posição de uma expressão multi-result importa: em muitas listas somente a última pode expandir para vários valores. Entenda essa regra em `return`, calls, constructors e varargs, pois parênteses ou mudança de posição podem reduzir deliberadamente a um resultado.
