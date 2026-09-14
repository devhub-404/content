# Modelo de Garbage Collection

Lua libera objetos managed unreachable automáticamente. Lua 5.5 mantiene modos de collector y cambia major collections a comportamiento incremental, reduciendo la necesidad de una gran pausa única en el modelo ordinario.

```lua
local data = {}

for i = 1, 1000 do
    data[i] = {value = i}
end

data = nil
collectgarbage("collect")
```

No fuerces full collection rutinariamente sin evidencia. `collectgarbage` expone tuning, pero los defaults suelen bastar. El crecimiento de memoria suele venir de datos aún reachable —caches, globals, closures, registries o referencias del host— y no de objetos olvidados por el collector.
