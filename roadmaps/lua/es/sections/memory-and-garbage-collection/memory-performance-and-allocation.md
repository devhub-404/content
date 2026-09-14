# Asignación y Lua Consciente de Memoria

Tables, closures, strings y userdata tienen costes de allocation, pero la optimización debe empezar con medición. `table.create` de Lua 5.5 puede preasignar capacity y los hosts pueden instalar allocators personalizados mediante la C API.

```lua
local items = table.create(1000, 0)

for i = 1, 1000 do
    items[i] = i * 2
end
```

Evita convertir código ordinario en microgestión antes de encontrar el hot path real. Reutilizar buffers, evitar temporary tables en loops y elegir representaciones compactas puede ayudar, pero el algoritmo y los costes de frontera con el host suelen dominar pequeños ahorros sintácticos.
