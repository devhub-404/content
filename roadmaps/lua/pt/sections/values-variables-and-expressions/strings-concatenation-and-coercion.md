# Strings, Concatenação e Conversão

Strings em Lua são sequências imutáveis de bytes e podem conter bytes arbitrários, inclusive zero. `..` concatena e `#` retorna o comprimento em bytes. Strings com aspas suportam escapes e long brackets são úteis para texto multilinha.

```lua
local language = "Lua"
local version = 5.5

local label = language .. " " .. tostring(version)
print(label)
print(#label)
```

Use `tostring` e `tonumber` quando conversão faz parte da intenção, em vez de depender de coerções implícitas históricas. Encoding é responsabilidade da aplicação; a library `utf8` ajuda com code points UTF-8, enquanto operações básicas continuam byte-oriented.
