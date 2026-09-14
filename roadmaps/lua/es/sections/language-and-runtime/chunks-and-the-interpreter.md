# Chunks y el Intérprete Standalone

Lua ejecuta source como chunks. Un archivo es un chunk, pero un chunk también puede venir de una string o de código cargado por una aplicación host. El programa standalone `lua` carga y ejecuta chunks y expone argumentos de línea de comandos mediante la table convencional `arg`.

```lua
-- hello.lua
local name = arg[1] or "world"
print("Hello, " .. name)
```

Un chunk se compila antes de ejecutarse y se comporta de forma parecida al cuerpo de una función variádica. Esto importa al usar `load`, modules, environments personalizados o la C API: Lua no se limita a “ejecutar archivos”; un host puede cargar código bajo condiciones controladas.
