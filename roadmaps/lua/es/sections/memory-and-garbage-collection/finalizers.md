# Finalizers y `__gc`

Algunos valores participan en finalization mediante `__gc`. Los finalizers se ejecutan como parte del garbage collector, por lo que su momento no es un boundary determinista de scope y no deben ser el mecanismo principal para recursos que deban liberarse pronto.

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

Prefiere close explícito y variables to-be-closed para files, locks y host handles escasos. Los finalizers sirven como safety net o para cleanup sin timing importante. Evita resurrection y dependencias complejas entre finalizers.
