# Finalizers and `__gc`

Some values can participate in finalization through `__gc`. Finalizers run as part of garbage-collection processing, so their timing is not a deterministic scope boundary and they should not be the primary mechanism for resources that must be released promptly.

```lua
local mt = {
    __gc = function(object)
        print("finalizing", object.name)
    end
}

local object = setmetatable({
    name = "resource"
}, mt)
```

Prefer explicit close operations and to-be-closed variables for files, locks, or scarce host handles. Finalizers are useful as a last safety net or for cleanup whose timing is not important. Keep them robust because complex resurrection or dependencies between finalizers make lifecycle reasoning difficult.
