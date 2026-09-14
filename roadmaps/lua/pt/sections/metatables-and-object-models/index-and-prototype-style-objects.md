# `__index` e Objetos Prototype-style

O metamethod `__index` pode redirecionar field ausente para outra table ou function. Um padrão comum define `Class.__index = Class` e usa essa table como metatable das instâncias, compartilhando methods.

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

Isso é convenção, não class system built-in. `obj:method(x)` apenas passa `obj` como primeiro argumento. Use o padrão quando ajuda o domínio; records simples com functions/closures podem ser melhores em modules pequenos.
