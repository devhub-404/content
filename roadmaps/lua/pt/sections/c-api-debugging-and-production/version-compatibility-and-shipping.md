# Compatibilidade de Versões e Distribuição

Releases dentro da mesma minor line são projetadas para compatibilidade, mas versões diferentes podem mudar APIs, bytecode e detalhes da C ABI. Chunks precompiled não devem ser tratados como portáveis entre versões.

```lua
local major, minor = _VERSION:match("Lua (%d+)%.(%d+)")

print("Lua version:", major, minor)
```

Produto embedded deve documentar a language line suportada e rebuildar native modules quando ABI exigir. Prefira source chunks salvo decisão deliberada por bytecode version-coupled. Teste scripts com as mesmas libraries/capabilities de produção.
