# `if`, `while`, `repeat` e `for`

Lua possui statements convencionais: `if`, `while`, `repeat ... until`, numeric `for` e generic `for`. Numeric `for` avalia bounds antes do loop e, no Lua 5.5, suas control variables são read-only.

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

`repeat` verifica a condição depois do corpo e portanto executa ao menos uma vez. `break` sai do loop e `goto` pode saltar para label visível quando isso realmente simplifica controle. Prefira loops estruturados e funções pequenas.
