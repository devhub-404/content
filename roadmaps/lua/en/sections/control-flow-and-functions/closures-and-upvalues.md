# Closures and Upvalues

A function can capture locals from an enclosing lexical scope. Those captured variables are called upvalues and remain alive as long as a closure can still access them. This gives Lua a natural way to create private state without a class mechanism.

```lua
local function counter()
    local value = 0

    return function()
        value = value + 1
        return value
    end
end

local next_value = counter()
print(next_value())
print(next_value())
```

Closures power callbacks, iterators, module-private state, factories, and event handlers. Remember that closures capture variables, not frozen snapshots of values: several closures may intentionally share one upvalue, and mutation through one closure becomes visible to the others.
