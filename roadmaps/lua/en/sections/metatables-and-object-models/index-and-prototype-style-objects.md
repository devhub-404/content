# `__index` and Prototype-style Objects

The `__index` metamethod can redirect a missing table field to another table or function. A common Lua object pattern sets `Class.__index = Class` and gives each instance that table as its metatable, so methods are shared instead of copied into every object.

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

This is a convention, not a built-in class system. The colon syntax `obj:method(x)` simply passes `obj` as the first argument. Use this pattern when it helps the domain, but plain records plus functions or closures can be simpler for small modules.
