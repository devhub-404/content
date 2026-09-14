# Metatables e Metamethods

Metatable associa comportamento especial a tables e userdata. Metamethods como `__index`, `__newindex`, operadores, comparisons, `__call` e `__tostring` participam quando a operação comum precisa de comportamento customizado.

```lua
local point_mt = {}

function point_mt.__tostring(p)
    return ("(%d, %d)"):format(p.x, p.y)
end

local p = setmetatable({x = 3, y = 4}, point_mt)
print(p)
```

Metamethods devem tornar abstração natural, não surpreender. Mantenha metatable private quando callers devem usar apenas API. Operações raw como `rawget`/`rawset` ignoram partes do comportamento e ajudam implementações low-level.
