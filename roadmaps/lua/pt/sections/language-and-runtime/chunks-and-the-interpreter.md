# Chunks e o Interpretador Standalone

Lua executa source como chunks. Um arquivo é um chunk, mas um chunk também pode vir de uma string ou de código carregado por uma aplicação host. O programa standalone `lua` carrega e executa chunks e expõe argumentos de linha de comando pela table convencional `arg`.

```lua
-- hello.lua
local name = arg[1] or "world"
print("Hello, " .. name)
```

Um chunk é compilado antes de executar e se comporta de forma parecida com o corpo de uma função variádica. Isso importa ao usar `load`, modules, environments customizados ou a C API: Lua não se limita a “executar arquivos”; um host pode carregar código sob condições controladas.
