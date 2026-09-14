# The C API Stack Model

The Lua C API communicates most values through a virtual stack owned by a `lua_State`. C code pushes arguments or results, reads values by stack index, calls Lua functions, and returns a count of results for native functions exposed to Lua.

```lua
-- Conceptual Lua side:
local result = native.add(20, 22)
print(result)
```

Stack discipline is the foundation of correct bindings. Track how many values every API call pushes or removes, use type-checking helper functions where appropriate, and restore the expected stack shape on all paths. A wrong stack index can turn a simple binding bug into a difficult native crash.
