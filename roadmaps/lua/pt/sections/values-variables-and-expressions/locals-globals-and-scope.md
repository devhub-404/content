# Locals, Globals e Escopo Léxico

Lua usa escopo léxico para variáveis locais. Um binding `local` fica visível da declaração até o fim do bloco e blocos internos podem fazer shadow. Functions definidas dentro do scope podem continuar usando locals como upvalues após o retorno externo.

```lua
local count = 10

do
    local count = 20
    print(count) -- 20
end

print(count) -- 10
```

Globals normalmente são fields do environment atual. Lua 5.5 também adiciona declarações de global, permitindo controlar explicitamente free names. Prefira locals por default: dependências ficam claras, estado compartilhado acidental diminui e o acesso normalmente é mais eficiente.
