# `require` e Modules

Modules Lua são convenções construídas sobre chunks, valores e `require`. Um arquivo normalmente cria table local de public functions e a retorna. `require` procura loaders configurados, executa o module, faz cache do resultado e retorna o valor carregado.

```lua
-- greeting.lua
local M = {}

function M.hello(name)
    return "Hello, " .. name
end

return M
```

Mantenha implementation details locais e retorne apenas a API pública. Module não precisa criar global table com seu nome. O padrão oferece encapsulamento simples, evita poluir globals e deixa dependências explícitas.
