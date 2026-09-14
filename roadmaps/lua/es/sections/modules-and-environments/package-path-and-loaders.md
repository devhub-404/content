# `package.path`, `package.cpath` y Searchers

La library `package` controla la carga de modules. `package.path` contiene patterns para source Lua y `package.cpath` para modules C. Los searchers determinan la resolución y `package.loaded` registra los modules cargados.

```lua
print(package.path)
print(package.cpath)

local json = require("json")
```

Las aplicaciones deben configurar paths deliberadamente en vez de depender del current working directory. Los hosts embedded pueden instalar searchers personalizados para cargar código desde assets, archives u otras fuentes controladas sin exponer todo el filesystem.
