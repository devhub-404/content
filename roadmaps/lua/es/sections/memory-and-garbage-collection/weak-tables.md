# Weak Tables

Una table puede mantener weak keys, weak values o ambos mediante `__mode` en su metatable. Las weak references no mantienen vivos los objetos seleccionados solo por aparecer en la table, lo que sirve para caches y asociaciones ligadas al lifetime de otro objeto.

```lua
local cache = setmetatable({}, {
    __mode = "v"
})

local object = {name = "temporary"}
cache.key = object

object = nil
collectgarbage()
```

Las reglas son precisas, especialmente para strings, finalizers y ephemeron behavior. Usa weak tables solo cuando la relación de ownership sea realmente non-owning; las tables normales son más fáciles de razonar para estado ordinario.
