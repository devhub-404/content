# Closures e Upvalues

Uma function pode capturar locals de um scope léxico externo. Essas variáveis capturadas são upvalues e permanecem vivas enquanto alguma closure puder acessá-las. Isso cria estado privado naturalmente sem mecanismo de classes.

```lua
local function counter()
    local value = 0

    return function()
        value = value + 1
        return value
    end
end

local next_value = counter()
print(next_value())
print(next_value())
```

Closures sustentam callbacks, iterators, module-private state, factories e handlers. Elas capturam variáveis, não snapshots congelados: várias closures podem compartilhar o mesmo upvalue e mutation por uma fica visível às outras.
