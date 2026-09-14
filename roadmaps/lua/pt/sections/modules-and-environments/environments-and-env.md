# Environments e `_ENV`

Acesso a global names em Lua é definido por environment, representado pelo mecanismo `_ENV`. Carregar chunk com environment customizado muda quais globals ele pode enxergar e atribuir, útil para configuração e scripting embedded.

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

Environment sozinho não é sandbox completa. Se expõe função capaz de acessar filesystem, process, debug library ou internals do host, o código pode usar essa capacidade. Projete por capabilities e audite cada valor exposto.
