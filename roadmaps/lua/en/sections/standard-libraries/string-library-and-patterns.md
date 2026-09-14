# String Library and Lua Patterns

The `string` library provides byte-oriented substring, search, formatting, case conversion, replacement, packing, and pattern matching. Lua patterns are a compact pattern language with captures and character classes; they are not Perl-compatible regular expressions.

```lua
local text = "user:42"

local name, id = text:match("^(%a+):(%d+)$")

print(name, id)

local cleaned = text:gsub("%d+", "<id>")
print(cleaned)
```

Patterns are excellent for moderate text extraction and replacement, but do not force a large grammar or deeply nested structured format into one pattern. Remember that string positions are byte indexes. For Unicode-aware character operations, combine the `utf8` library or a higher-level text library with the application's encoding rules.
