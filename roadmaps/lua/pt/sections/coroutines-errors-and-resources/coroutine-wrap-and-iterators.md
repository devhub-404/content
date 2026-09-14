# `coroutine.wrap` e Iterators Baseados em Coroutine

`coroutine.wrap` transforma uma coroutine em function que faz resume a cada chamada e retorna yielded values diretamente. Isso torna certos producer iterators concisos porque o estado fica em locals suspensos.

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

Wrapped coroutines reportam errors de forma diferente de `resume`, então escolha conforme controle e diagnostics. Para iteração simples, closure ou generic-for iterator pode ser mais claro; use coroutine quando suspensão representa naturalmente o estado.
