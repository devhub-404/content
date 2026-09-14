# Operator and Call Metamethods

Metamethods let user values participate in arithmetic, concatenation, comparisons, length, and function-call syntax. This can produce compact domain types such as vectors, matrices, symbolic values, or callable configuration objects.

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

Only overload an operation when its meaning will be obvious to a reader. Comparison metamethods have consistency requirements, and custom equality/ordering can interact with algorithms or table usage in ways that need careful design. A named method is often clearer than a clever operator.
