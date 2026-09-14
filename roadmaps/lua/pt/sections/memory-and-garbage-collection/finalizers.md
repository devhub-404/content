# Finalizers e `__gc`

Alguns valores participam de finalization por `__gc`. Finalizers executam como parte do garbage collector, então o momento não é uma boundary determinística de scope e não deve ser o mecanismo principal para recursos que precisam de liberação rápida.

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

Prefira close explícito e to-be-closed variables para files, locks e host handles escassos. Finalizers funcionam como safety net ou cleanup sem timing importante. Evite resurrection e dependências complexas entre finalizers.
