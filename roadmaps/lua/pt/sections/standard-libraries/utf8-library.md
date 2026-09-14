# Library UTF-8

A library `utf8` fornece operações básicas sobre encoding UTF-8, incluindo length validado, conversão de code points, iteração e offsets. Ela trabalha com code points enquanto strings Lua comuns continuam sendo byte sequences.

```lua
local text = "Olá, 世界"

print(utf8.len(text))

for position, codepoint in utf8.codes(text) do
    print(position, codepoint)
end
```

Um code point não é sempre um caractere percebido; combining marks e emoji podem conter vários. Para grapheme segmentation, locale-aware casing, collation ou normalization, use library Unicode de nível mais alto.
