# Alocação e Lua Consciente de Memória

Tables, closures, strings e userdata possuem custos de allocation, mas otimização deve começar por medição. `table.create` do Lua 5.5 pode pré-alocar capacity e hosts podem instalar allocators customizados pela C API.

```lua
local items = table.create(1000, 0)

for i = 1, 1000 do
    items[i] = i * 2
end
```

Evite transformar código comum em microgerenciamento antes de encontrar hot path real. Reuse de buffers, evitar temporary tables em loops e representações compactas podem ajudar, mas algoritmo e host-boundary costs frequentemente dominam pequenas economias sintáticas.
