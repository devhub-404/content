# `coroutine.wrap` e Iterators Basados en Coroutine

`coroutine.wrap` convierte una coroutine en una function que hace resume en cada llamada y devuelve los yielded values directamente. Esto hace concisos ciertos iterators productores porque el estado queda en locals suspendidos.

```lua
local function values()
    return coroutine.wrap(function()
        coroutine.yield("a")
        coroutine.yield("b")
        coroutine.yield("c")
    end)
end

local next_value = values()
print(next_value())
print(next_value())
```

Las wrapped coroutines reportan errors de forma distinta a `resume`, así que elige según control y diagnostics. Para iteración simple, una closure o generic-for iterator puede ser más claro; usa coroutine cuando la suspensión modele naturalmente el estado.
