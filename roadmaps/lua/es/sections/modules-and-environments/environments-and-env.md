# Environments y `_ENV`

El acceso a global names en Lua se define mediante un environment, representado por `_ENV`. Cargar un chunk con un environment personalizado cambia qué globals puede ver y asignar, útil para configuración y scripting embedded.

```lua
local env = {
    print = print,
    answer = 42,
}

local fn = assert(load(
    "print(answer)",
    "example",
    "t",
    env
))

fn()
```

Un environment por sí solo no es un sandbox completo. Si expone una función capaz de acceder al filesystem, process, debug library o internals del host, el código puede usar esa capacidad. Diseña por capabilities y audita cada valor expuesto.
