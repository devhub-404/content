# A Library `table`

A library `table` contém operações comuns para tables sequence-like, incluindo sort, insert, remove, move, pack/unpack, concat e, no Lua 5.5, criação pré-alocada com `table.create`. Cada função assume a forma de table descrita em seu contrato.

```lua
local values = {3, 1, 2}

table.sort(values)
table.insert(values, 4)

print(table.concat(values, ", "))

local last = table.remove(values)
print(last)
```

Sorting pode receber comparator e ele precisa definir ordem consistente. Insert/remove repetidos no meio de sequence grande deslocam elementos, então escolha representação conforme operações reais quando performance importar.
