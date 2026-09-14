# Metatables and Metamethods

A metatable associates special behavior with tables and userdata. Metamethod fields such as `__index`, `__newindex`, arithmetic operators, comparison hooks, `__call`, and `__tostring` participate when the corresponding ordinary operation needs custom behavior.

```lua
local point_mt = {}

function point_mt.__tostring(p)
    return ("(%d, %d)"):format(p.x, p.y)
end

local p = setmetatable({x = 3, y = 4}, point_mt)
print(p)
```

Metamethods should make an abstraction feel natural, not make ordinary syntax surprising. Keep the metatable itself private when callers should interact only through the abstraction. Raw operations such as `rawget` and `rawset` bypass selected metamethod behavior and are useful inside low-level implementations.
