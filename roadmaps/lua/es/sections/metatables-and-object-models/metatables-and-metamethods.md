# Metatables y Metamethods

Una metatable asocia comportamiento especial a tables y userdata. Metamethods como `__index`, `__newindex`, operadores, comparisons, `__call` y `__tostring` participan cuando la operación ordinaria necesita comportamiento personalizado.

```lua
local point_mt = {}

function point_mt.__tostring(p)
    return ("(%d, %d)"):format(p.x, p.y)
end

local p = setmetatable({x = 3, y = 4}, point_mt)
print(p)
```

Los metamethods deben hacer natural la abstracción, no sorprender. Mantén la metatable private cuando los callers deban usar solo la API. Operaciones raw como `rawget`/`rawset` omiten parte del comportamiento y ayudan a implementaciones low-level.
