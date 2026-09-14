# Tipos, `nil` y Truthiness

Los principales tipos de valor incluyen nil, boolean, number, string, function, userdata, thread y table. Las variables no tienen un value type fijo declarado; un local puede referirse a tipos distintos a lo largo del tiempo. `type(value)` informa el tipo en runtime.

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

Solo `false` y `nil` son falsos en condiciones. Cero, la string vacía y una table vacía son truthy. `nil` también representa ausencia de un field en una table y muchas APIs lo usan como “sin valor”, así que distingue ausencia de false o cero significativos.
