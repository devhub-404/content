# Varargs y Named Vararg Tables

Las functions variádicas aceptan argumentos extra mediante `...`. Lua 5.5 añade un nombre opcional después de `...`; ese nombre se refiere a una vararg table read-only con entradas numéricas y un field `n` que conserva el count exacto, incluso con nil finales.

```lua
local function describe(prefix, ... args)
    print(prefix, args.n)

    for i = 1, args.n do
        print(i, args[i])
    end
end

describe("values", 10, 20, nil)
```

Las expresiones `...` anónimas siguen funcionando con las reglas de multiple results. Las named vararg tables ayudan cuando necesitas indexar/contar argumentos. Para muchas options sin relación posicional, una options table normal suele ser más clara.
