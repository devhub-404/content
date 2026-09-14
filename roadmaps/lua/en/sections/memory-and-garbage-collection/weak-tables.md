# Weak Tables

A table can hold weak keys, weak values, or both when its metatable's `__mode` field requests it. Weak references do not keep selected objects alive solely because they appear in that table, which is useful for caches and associations tied to another object's lifetime.

```lua
local cache = setmetatable({}, {
    __mode = "v"
})

local object = {name = "temporary"}
cache.key = object

object = nil
collectgarbage()
```

Weakness has precise rules, especially around strings, values with finalizers, and ephemeron behavior for weak-key tables. Use weak tables only when the desired ownership relationship is truly non-owning; ordinary tables are easier to reason about for normal application state.
