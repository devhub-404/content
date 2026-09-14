# Types, `nil`, and Truthiness

Lua's main value types include nil, boolean, number, string, function, userdata, thread, and table. Variables do not have fixed declared value types; a local can refer to values of different types over time. `type(value)` reports the runtime type name.

```lua
local values = {
    type(nil),
    type(true),
    type(42),
    type("lua"),
    type({}),
    type(function() end),
}

for _, value in ipairs(values) do
    print(value)
end
```

Only `false` and `nil` are false in conditions. Zero, the empty string, and empty tables are all truthy. `nil` also represents the absence of a table field and is used by many APIs to mean “no value,” so distinguish absence from meaningful false or zero values.
