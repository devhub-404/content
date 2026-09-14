# Modelo de Stack da C API

A C API comunica a maioria dos valores por uma stack virtual pertencente a `lua_State`. Código C push/read valores por índices, chama functions Lua e retorna count de results em native functions expostas.

```lua
-- Conceptual Lua side:
local result = native.add(20, 22)
print(result)
```

Disciplina da stack é base de binding correto. Acompanhe quantos valores cada API call adiciona/remove, use helpers de type-check e restaure o shape esperado em todos os paths. Índice errado pode virar crash nativo difícil.
