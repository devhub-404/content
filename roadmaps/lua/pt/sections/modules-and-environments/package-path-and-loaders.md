# `package.path`, `package.cpath` e Searchers

A library `package` controla carregamento de modules. `package.path` contém patterns para source Lua e `package.cpath` para modules C. Searchers determinam resolução e `package.loaded` registra modules carregados.

```lua
print(package.path)
print(package.cpath)

local json = require("json")
```

Aplicações devem configurar paths deliberadamente em vez de depender do current working directory. Hosts embedded podem instalar searchers customizados para carregar código de assets, archives ou fontes controladas sem expor todo o filesystem.
