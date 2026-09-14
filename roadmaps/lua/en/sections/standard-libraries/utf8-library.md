# UTF-8 Library

The `utf8` library provides basic operations over UTF-8 encodings, including validation-aware length, code-point conversion, iteration, and offset calculations. It works with Unicode code points while ordinary Lua strings remain byte sequences.

```lua
local text = "Olá, 世界"

print(utf8.len(text))

for position, codepoint in utf8.codes(text) do
    print(position, codepoint)
end
```

A Unicode code point is not always one user-perceived character; combining marks and emoji sequences can contain several code points. If the application needs grapheme segmentation, locale-aware case mapping, collation, or normalization, use a library designed for those higher-level Unicode operations.
