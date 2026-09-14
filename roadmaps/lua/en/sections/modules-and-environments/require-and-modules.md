# `require` and Modules

Lua modules are conventions built around chunks, values, and `require`. A module file commonly creates a local table of public functions and returns it. `require` searches configured loaders, executes the module once for that package entry, caches the result, and returns the loaded value.

```lua
-- greeting.lua
local M = {}

function M.hello(name)
    return "Hello, " .. name
end

return M
```

Keep implementation details local and return only the public API. A module does not need a global table with its name. This pattern gives simple encapsulation, avoids global namespace pollution, and makes dependencies explicit at the call site.
