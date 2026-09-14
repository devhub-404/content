# Metamethods de Operadores e Chamada

Metamethods permitem que valores participem de aritmética, concatenação, comparisons, length e call syntax. Isso cria domain types compactos como vectors, matrices ou objetos callable.

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

Só overload uma operação quando o significado for óbvio. Comparison metamethods exigem consistência e podem interagir com algorithms/tables de forma sutil. Muitas vezes um método nomeado é mais claro que operador clever.
