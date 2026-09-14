# Modelo de Garbage Collection

Lua libera objetos managed unreachable automaticamente. Lua 5.5 mantém modos de collector e passa major collections a comportamento incremental, reduzindo necessidade de uma grande pausa única no modelo comum.

```lua
local data = {}

for i = 1, 1000 do
    data[i] = {value = i}
end

data = nil
collectgarbage("collect")
```

Não force full collection rotineiramente sem evidência. `collectgarbage` expõe tuning, mas defaults normalmente bastam. Crescimento de memória frequentemente vem de dados ainda reachable — caches, globals, closures, registries ou host references — e não de objetos esquecidos pelo collector.
