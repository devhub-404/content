# `__index` y Objetos Prototype-style

El metamethod `__index` puede redirigir un field ausente a otra table o function. Un patrón común define `Class.__index = Class` y usa esa table como metatable de las instancias, compartiendo methods.

```lua
local Account = {}
Account.__index = Account

function Account.new(balance)
    return setmetatable({
        balance = balance or 0
    }, Account)
end

function Account:deposit(amount)
    self.balance = self.balance + amount
end
```

Es una convención, no un class system built-in. `obj:method(x)` simplemente pasa `obj` como primer argumento. Usa el patrón cuando ayude al dominio; records simples con functions/closures pueden ser mejores en modules pequeños.
