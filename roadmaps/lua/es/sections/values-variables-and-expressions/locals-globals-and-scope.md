# Locals, Globals y Scope Léxico

Lua usa scope léxico para variables locales. Un binding `local` es visible desde su declaración hasta el final del bloque y los bloques internos pueden hacer shadow. Las functions definidas dentro del scope pueden seguir usando locals como upvalues después del retorno externo.

```lua
local count = 10

do
    local count = 20
    print(count) -- 20
end

print(count) -- 10
```

Los globals suelen ser fields del environment actual. Lua 5.5 también añade declaraciones de global, permitiendo controlar explícitamente los free names. Prefiere locals por defecto: las dependencias quedan claras, se evita estado compartido accidental y el acceso suele ser más eficiente.
