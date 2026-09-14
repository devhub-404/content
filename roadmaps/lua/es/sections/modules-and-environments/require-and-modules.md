# `require` y Modules

Los modules Lua son convenciones construidas sobre chunks, valores y `require`. Un archivo suele crear una table local de public functions y retornarla. `require` busca loaders configurados, ejecuta el module, cachea el resultado y devuelve el valor cargado.

```lua
-- greeting.lua
local M = {}

function M.hello(name)
    return "Hello, " .. name
end

return M
```

Mantén implementation details locales y retorna solo la API pública. Un module no necesita crear una global table con su nombre. Este patrón ofrece encapsulación simple, evita contaminar globals y hace explícitas las dependencias.
