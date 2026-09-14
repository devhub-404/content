# Library de String e Lua Patterns

A library `string` fornece substring, busca, formatting, case conversion, replacement, packing e pattern matching byte-oriented. Lua patterns são linguagem compacta com captures/classes; não são regex Perl-compatible.

```lua
local text = "user:42"

local name, id = text:match("^(%a+):(%d+)$")

print(name, id)

local cleaned = text:gsub("%d+", "<id>")
print(cleaned)
```

Patterns funcionam bem para extração/substituição moderada, mas não force gramática grande em um pattern. Posições de string são byte indexes. Para Unicode, combine `utf8` ou library de texto adequada.
