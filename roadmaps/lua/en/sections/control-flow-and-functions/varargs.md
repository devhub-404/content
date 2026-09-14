# Varargs and Named Vararg Tables

Variadic functions accept extra arguments through `...`. Lua 5.5 adds an optional name after `...`; that name refers to a read-only vararg table with numeric entries and an `n` field that preserves the exact argument count, including trailing nil values.

```lua
local function describe(prefix, ... args)
    print(prefix, args.n)

    for i = 1, args.n do
        print(i, args[i])
    end
end

describe("values", 10, 20, nil)
```

Anonymous `...` expressions still work and participate in Lua's multiple-result adjustment rules. Named vararg tables are useful when arguments need indexing or counting. For APIs with many unrelated optional settings, a normal options table is usually clearer than a long positional vararg convention.
