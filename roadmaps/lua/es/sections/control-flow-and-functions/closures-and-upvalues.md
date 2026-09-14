# Closures y Upvalues

Una function puede capturar locals de un scope léxico exterior. Estas variables capturadas se llaman upvalues y permanecen vivas mientras alguna closure pueda accederlas. Esto permite crear estado privado naturalmente sin un mecanismo de clases.

```lua
local function counter()
    local value = 0

    return function()
        value = value + 1
        return value
    end
end

local next_value = counter()
print(next_value())
print(next_value())
```

Las closures sustentan callbacks, iterators, estado privado de módulos, factories y handlers. Capturan variables, no snapshots congelados: varias closures pueden compartir el mismo upvalue y la mutation mediante una será visible para las demás.
