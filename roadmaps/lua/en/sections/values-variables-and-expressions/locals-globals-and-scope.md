# Locals, Globals, and Lexical Scope

Lua uses lexical scope for local variables. A `local` binding is visible from its declaration through the containing block, and inner blocks may shadow outer names. Functions defined inside a scope can keep using its locals as upvalues after that scope would otherwise have returned.

```lua
local count = 10

do
    local count = 20
    print(count) -- 20
end

print(count) -- 10
```

Globals are normally fields in the current environment. Lua 5.5 also adds global declarations, which let a scope explicitly control which free names are global. Prefer locals by default: they make dependencies clearer, avoid accidental shared state, and are usually faster to access.
