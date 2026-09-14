# Weak Tables

Uma table pode manter weak keys, weak values ou ambos via `__mode` em sua metatable. Weak references não mantêm os objetos selecionados vivos apenas por aparecerem na table, sendo úteis em caches e associações ligadas ao lifetime de outro objeto.

```lua
local cache = setmetatable({}, {
    __mode = "v"
})

local object = {name = "temporary"}
cache.key = object

object = nil
collectgarbage()
```

As regras são precisas, especialmente para strings, finalizers e ephemeron behavior. Use weak tables apenas quando a relação de ownership é realmente non-owning; tables comuns são mais simples para estado normal.
