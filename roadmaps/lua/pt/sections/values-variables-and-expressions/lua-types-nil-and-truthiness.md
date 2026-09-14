# Tipos, `nil` e Truthiness

Os principais tipos de valor incluem nil, boolean, number, string, function, userdata, thread e table. Variáveis não possuem um value type fixo declarado; um local pode referir-se a tipos diferentes ao longo do tempo. `type(value)` informa o tipo em runtime.

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

Somente `false` e `nil` são falsos em condições. Zero, string vazia e table vazia são truthy. `nil` também representa ausência de field em table e é usado por muitas APIs como “sem valor”, então diferencie ausência de false ou zero significativos.
