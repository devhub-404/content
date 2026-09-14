# Varargs e Named Vararg Tables

Functions variádicas aceitam argumentos extras por `...`. Lua 5.5 adiciona um nome opcional após `...`; esse nome refere-se a uma vararg table read-only com entries numéricas e field `n`, preservando count exato inclusive com nils finais.

```lua
local function describe(prefix, ... args)
    print(prefix, args.n)

    for i = 1, args.n do
        print(i, args[i])
    end
end

describe("values", 10, 20, nil)
```

Expressões `...` anônimas continuam funcionando com as regras de multiple results. Named vararg tables ajudam quando precisa indexar/contar argumentos. Para muitas options sem relação posicional, uma options table normal costuma ser mais clara.
