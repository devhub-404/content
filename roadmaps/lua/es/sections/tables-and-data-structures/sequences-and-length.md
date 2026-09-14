# Sequences, Claves Enteras y Length

Lua representa arrays convencionalmente como tables con claves enteras empezando en 1. Una sequence tiene un border bien definido para claves consecutivas y `#` es fiable para sequences adecuadas, no para tables sparse arbitrarias.

```lua
local colors = {"red", "green", "blue"}

print(colors[1])
print(#colors)

colors[#colors + 1] = "gold"
```

No crees holes y después supongas que `#` tiene una única respuesta obvia. Usa un count explícito u otra representación para datos sparse. Lua 5.5 también ofrece `table.create` para preasignar capacity cuando aporta un beneficio medido.
