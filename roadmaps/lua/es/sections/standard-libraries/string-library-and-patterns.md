# Library de String y Lua Patterns

La library `string` ofrece substring, búsqueda, formatting, case conversion, replacement, packing y pattern matching orientados a bytes. Los Lua patterns son un lenguaje compacto con captures/clases; no son regex compatibles con Perl.

```lua
local text = "user:42"

local name, id = text:match("^(%a+):(%d+)$")

print(name, id)

local cleaned = text:gsub("%d+", "<id>")
print(cleaned)
```

Los patterns funcionan bien para extracción/sustitución moderada, pero no fuerces una gramática grande en un solo pattern. Las posiciones de string son índices de bytes. Para Unicode, combina `utf8` o una library de texto adecuada.
