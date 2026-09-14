# Sequences, Integer Keys, and Length

Lua conventionally represents arrays as tables with integer keys starting at 1. A sequence is a table with a well-defined border for consecutive integer keys, and the length operator `#` is reliable for proper sequences rather than arbitrary sparse integer-keyed tables.

```lua
local colors = {"red", "green", "blue"}

print(colors[1])
print(#colors)

colors[#colors + 1] = "gold"
```

Do not create holes in a sequence and then assume `#` has one obvious mathematical answer. Use explicit counts or a different representation for sparse data. Lua 5.5 also provides `table.create` for preallocating expected sequence and record capacity when measurements show that it is useful.
