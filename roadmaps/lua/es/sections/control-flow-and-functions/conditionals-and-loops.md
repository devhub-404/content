# `if`, `while`, `repeat` y `for`

Lua ofrece statements convencionales: `if`, `while`, `repeat ... until`, numeric `for` y generic `for`. Numeric `for` evalúa sus límites antes del loop y, en Lua 5.5, sus control variables son read-only.

```lua
local total = 0

for i = 1, 5 do
    total = total + i
end

if total > 10 then
    print("large")
else
    print("small")
end
```

`repeat` comprueba la condición después del cuerpo y por eso se ejecuta al menos una vez. `break` sale del loop y `goto` puede saltar a un label visible cuando realmente simplifique el control. Prefiere loops estructurados y funciones pequeñas.
