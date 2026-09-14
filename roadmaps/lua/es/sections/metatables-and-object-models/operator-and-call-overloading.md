# Metamethods de Operadores y Llamada

Los metamethods permiten que valores participen en aritmética, concatenación, comparisons, length y call syntax. Esto crea domain types compactos como vectors, matrices u objetos callable.

```lua
local vector_mt = {}

function vector_mt.__add(a, b)
    return setmetatable({
        x = a.x + b.x,
        y = a.y + b.y,
    }, vector_mt)
end

local a = setmetatable({x = 1, y = 2}, vector_mt)
local b = setmetatable({x = 3, y = 4}, vector_mt)

local c = a + b
```

Sobrecarga una operación solo cuando su significado sea obvio. Los comparison metamethods exigen consistencia y pueden interactuar con algorithms/tables de forma sutil. Muchas veces un método con nombre es más claro que un operador clever.
