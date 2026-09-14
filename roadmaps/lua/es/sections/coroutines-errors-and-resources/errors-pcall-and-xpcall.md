# Errors, `pcall` y `xpcall`

Lua genera errors con `error`. `pcall` captura y devuelve un boolean de éxito seguido por resultados normales o el error object. `xpcall` además acepta un message handler, útil para adjuntar traceback.

```lua
local function parse()
    error("invalid input")
end

local ok, err = pcall(parse)

if not ok then
    print("failed:", err)
end
```

Usa protected calls en fronteras donde recovery/isolation tenga sentido, como plugins o requests. No envuelvas cada función solo para suprimir fallos. Conserva contexto y define qué capa se ocupa del logging/reporting.
