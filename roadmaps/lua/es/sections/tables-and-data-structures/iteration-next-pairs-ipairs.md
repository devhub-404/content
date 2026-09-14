# `next`, `pairs` e `ipairs`

`pairs` recorre entradas key/value usando el comportamiento de iteración de la table, mientras `ipairs` recorre claves enteras consecutivas desde 1 hasta la primera ausente. `next` es la operación primitiva detrás del recorrido ordinario.

```lua
local user = {name = "Mina", score = 10}

for key, value in pairs(user) do
    print(key, value)
end

local colors = {"red", "green"}

for index, value in ipairs(colors) do
    print(index, value)
end
```

El orden de una table iteration ordinaria no es sorted ni un contrato estable. Si el orden importa, recopila y ordena keys o mantén una sequence separada. Evita cambios estructurales durante el recorrido salvo cuando las reglas lo permitan explícitamente.
