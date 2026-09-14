# Strings, Concatenation, and Conversion

Lua strings are immutable byte sequences and may contain arbitrary bytes, including zeros. The `..` operator concatenates strings and `#` returns the byte length for a string. Quoted strings support escapes, while long-bracket strings are convenient for multiline text without most escaping.

```lua
local language = "Lua"
local version = 5.5

local label = language .. " " .. tostring(version)
print(label)
print(#label)
```

Use `tostring` and `tonumber` when conversion is part of the program's intent instead of depending on legacy coercion habits. Text encoding is an application concern; the standard `utf8` library helps work with UTF-8 code points, while ordinary string indexing and lengths remain byte-oriented.
