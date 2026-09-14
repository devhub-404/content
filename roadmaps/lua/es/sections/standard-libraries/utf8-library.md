# Library UTF-8

La library `utf8` ofrece operaciones básicas sobre encoding UTF-8, incluidos length validado, conversión de code points, iteración y offsets. Trabaja con code points mientras las strings Lua ordinarias siguen siendo secuencias de bytes.

```lua
local text = "Olá, 世界"

print(utf8.len(text))

for position, codepoint in utf8.codes(text) do
    print(position, codepoint)
end
```

Un code point no siempre es un carácter percibido; combining marks y emoji pueden contener varios. Para grapheme segmentation, locale-aware casing, collation o normalization, usa una library Unicode de nivel superior.
