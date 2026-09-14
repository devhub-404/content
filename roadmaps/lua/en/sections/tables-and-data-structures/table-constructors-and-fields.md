# Table Constructors and Fields

Tables are Lua's only built-in general-purpose data structure. Keys can be most Lua values except nil and NaN, and values may have any type. Field syntax `t.name` is shorthand for `t["name"]`, so record-like objects are ordinary tables with string keys.

```lua
local user = {
    id = 42,
    name = "Mina",
    active = true,
}

print(user.name)
print(user["id"])
```

Assigning `nil` to a key removes that entry. A table is a reference-like object: assigning one table variable to another does not copy its contents. Decide explicitly when two parts of a program should share a table and when you need to construct an independent copy.
