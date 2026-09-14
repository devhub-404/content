# Errors, `pcall` e `xpcall`

Lua gera errors com `error`. `pcall` captura e retorna boolean de sucesso seguido por results normais ou error object. `xpcall` também aceita message handler, útil para anexar traceback.

```lua
local function parse()
    error("invalid input")
end

local ok, err = pcall(parse)

if not ok then
    print("failed:", err)
end
```

Use protected calls em fronteiras onde recovery/isolation faz sentido, como plugins ou requests. Não envolva toda função apenas para suprimir falhas. Preserve contexto e defina qual layer cuida de logging/reporting.
