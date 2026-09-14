# Modelo de Stack de la C API

La C API comunica la mayoría de valores mediante un stack virtual perteneciente a `lua_State`. El código C hace push/read por índices, llama functions Lua y retorna un count de results en native functions expuestas.

```lua
-- Conceptual Lua side:
local result = native.add(20, 22)
print(result)
```

La disciplina del stack es la base de un binding correcto. Controla cuántos valores añade o elimina cada API call, usa helpers de type-check y restaura el shape esperado en todos los paths. Un índice equivocado puede convertirse en un crash nativo difícil.
